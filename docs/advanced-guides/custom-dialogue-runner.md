# Building a Custom Dialogue Runner

> "Getting Additional Control Over The Dialogue or: How I Learned To Stop Worrying And Build My Own Custom Dialogue Runner Class"

{% hint style="warning" %}
This page describes advanced usage of Yarn Spinner. Unless you really need total control over how Yarn Spinner works in your Unity project, we recommend using the built-in [Dialogue Runner](../yarn-spinner-for-unity/components/dialogue-runner.md) class rather than creating your own.

If you really _do_ need total control, read on!
{% endhint %}

While for the most part we think the best way to use Yarn Spinner is to use the components provided and replace and supplement them as needed there are going to be times when you need more control over the dialogue itself. In these cases you will need to directly interface with the dialogue and to build your own dialogue runner. This will give you full control over the dialogue and let you control the timing and triggering of important events.

By the end of this guide we are going to have recreated the same scene and code as can be found in the [Minimal Viable Dialogue sample](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/tree/main/Samples~).

> :warning: **This guide is not for beginners**: You should be _very_ comfortable with Yarn Spinner and Unity before using this!

## The Depths of Yarn Spinner

Before we can really start building our own dialogue system we need to take a bit of a look at what Yarn Spinner does and how it works currently. The starting point for Yarn Spinner is the Yarn dialogue files themselves, once you have your Yarn files written and ready is where Yarn Spinner takes over. These files get associated together into a Yarn Project, this project reads through and compiles the Yarn files into three pieces:

* strings tables
* metadata table
* binary program

The strings table is a [CSV](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/Localization.cs) that holds all the text of the Yarn, the actual written dialogue. This isn't strictly necessary and could be stored in other parts of the output of the compilation but by having it separate it allows for easier localisation and proofing. The metadata table is similar, it is also a [CSV table](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/LineMetadata.cs) that holds all the metadata or hashtags each line of dialogue has. This metadata is used for a variety of reasons and changes on a game-by-game basis, as with the strings table this could be embedded in other elements but by having it standalone just simplifies certain elements. The binary program is a compiled representation of the Yarn as a series of [op codes](https://github.com/YarnSpinnerTool/YarnSpinner/blob/main/YarnSpinner/yarn_spinner.proto) as simulated on a stack machine. The binary program is the actual thing that Yarn Spinner will use to move through your dialogue, jump between nodes, create flow control, everything. Once the program has been compiled Yarn Spinner doesn't even look at the Yarn files.

These three pieces each have their own parts in what gets delivered to your game. The strings and metadata tables are used by the [Line Providers](https://docs.yarnspinner.dev/using-yarnspinner-with-unity/components/line-provider) to create the [LocalizedLines](https://docs.yarnspinner.dev/using-yarnspinner-with-unity/assets-and-localization) your views use, and the compiled program is used by the Dialogue class and the Dialogue Runner, in conjunction with the variable storage, to determine the story flow.

What this means is if we are making our own runner we can still use some of the existing pieces, especially the line providers, the variable storage, and the compiler itself. Now while you could make your own interface into this compiled output from scratch, unless you are porting Yarn Spinner over to an entirely different technology stack you'd be better off using the interface into it that the existing runner uses, the [Dialogue class](https://docs.yarnspinner.dev/api/csharp/yarn/yarn.dialogue). So that is what we will be doing in this guide.

### Lines and Providers

This isn't a deep dive into how the specifics of Yarn Spinner works there is one part that does need to be covered, and that is how lines work. When you write some lines in your Yarn like the following:

```
A: Oh hi there #line:ab12c
B: Hey #line:34de5
```

You have two lines (identified by their ids `ab12c` and `34de5`) that inside the strings table (simplified for this example) will be something like the following:

| ID    | Text        |
| ----- | ----------- |
| ab12c | Oh hi there |
| 34de5 | Hey         |

The compiled output of the yarn has no understanding or knowledge of the text itself, it just knows that it will at some point run a line with the id of `ab12c` and then after another line with the id of `34de5`. So to get the actual text this is where the line providers come in, they read the strings table and then return the actual text so that other parts of the game can use it. Even then there are further stages, substitutions need to occur and markup needs to be parsed, but the core is a line of text as far as the Yarn Spinner compiler is concerned is an id and nothing more, other pieces make it actual text. We do it this way for two main reasons, localisation and code bloat. If the text of the line was stored in the compiled program either we'd need to also store every localised variant also or have some other system to let the dialogue runner know that "no actually I know you have the line with some text but ignore it and use this text instead, thanks". Both of these approaches just makes the compiled output much much bigger and complicates the flow of the program, hence why we split them out.

## Our Dialogue Runner

The first thing before we make any new code is to decide how our custom dialogue runner is going to be different from the built-in one, for if its just the same why bother making it? The question now comes "what will our runner do that is different?" The current runner works by sending Dialogue Views information when important events occur and then relying on completion callbacks to control the flow. Every view gets told about important events and once every view has run their completion callback the runner continues. This means all timing is the responsibility of the views and that might be less than ideal for your needs, so lets change that in our runner. Let's make it so that all timing is solely the responsibility of the runner, and it won't give two hoots about what any other part of the game is doing, if its told to advance it will advance. With our goal set lets lay the basis of our scene.

1. If you have not already done so import Yarn Spinner
2. Create a new scene in Unity, name it whatever you like
3. Create a new C# file, name it `MinimalDialogueRunner.cs`
4. Open it and add the following:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Yarn.Unity;
using UnityEngine.Events;
using System.Linq;

public class MinimalDialogueRunner : MonoBehaviour
{
    public YarnProject project;
    public VariableStorageBehaviour VariableStorage;
    public LineProviderBehaviour LineProvider;

    public bool isRunning { get; internal set; } = false;

    private Yarn.Dialogue dialogue;
}
```

These are the basic bits we will need for our runner, in particular the `Yarn.Dialogue` is of most interest to us as it is how we will interface to the compiled version of the Yarn narrative.

### Handling the main events

Yarn can be thought of as an event driven story language, you start the story by going to a particular node in the story, then you advance through the story. Every time you reach a line of dialogue you show it (somehow), and then advance onto the next piece. When you hit a command you handle it (somehow), and then advance. When you hit a set of options you get the users input on which option to go with (somehow), and then advance. Eventually you finish that node and either end the story there or jump into a new node and start the process all over again. This gives us our main events we need to handle, lets stub them out now, add the following methods to our new runner:

```csharp
public void StartDialogue(string nodeName = "Start") {}
public void StopDialogue() {}
private void HandleOptions(Yarn.OptionSet options) {}
private void HandleCommand(Yarn.Command command) {}
private void HandleLine(Yarn.Line line) {}
private void HandleNodeStarted(string nodeName) {}
private void HandleNodeEnded(string nodeName) {}
private void HandleDialogueComplete() {}
public void Continue() {}
public void SetSelectedOption(int optionIndex) {}
```

Hopefully these are understandable enough from their names, but the public ones are intended to allow us as the game developer control the flow, and the private ones are for the runner itself to make use of before letting other parts of the game know what has happened. In general inside each of these methods we are going to be doing some setup and configuration so that when we let other parts of the game know everything is in a manner they can consume without too much work. Now there are two more events that aren't really events but should be handled, we need to let the line provider know to expect lines and we need to have a means of querying what nodes exist in the project, so we should add them now.

```csharp
private void PrepareForLines(IEnumerable<string> lineIDs) { LineProvider.PrepareForLines(lineIDs); }
public bool NodeExists(string nodeName) => dialogue.NodeExists(nodeName);
```

### Dispatch the events

Next step is to work out how to let the rest of the game know when important events have happened. While there are lots of ways we could do this, we will do this through the [`UnityEvent`](https://docs.unity3d.com/Manual/UnityEvents.html) system. We are going with Unity Events because they are super easy to create, you hook them up via the editor (which is nice), and their limitations won't bother us for this sample. We'll need six different events with various parameters so let's make them now:

```csharp
public UnityEvent<DialogueOption[]> OptionsNeedPresentation;
public UnityEvent<string[]> CommandNeedsHandling;
public UnityEvent<LocalizedLine> LineNeedsPresentation;
public UnityEvent<string> NodeStarted;
public UnityEvent<string> NodeEnded;
public UnityEvent DialogueComplete;
```

Each of these basically maps to a specific method we defined above and can be thought of as the public facing side of those methods. Ok now its time to draw the rest of the owl!

### Drawing the rest of the owl

Here we will be making the implementation of the methods we defined above and dispatching the events from inside of them, let's get cracking.

Replace the `StartDialogue` and `StopDialogue` methods with the following:

```csharp
public void StartDialogue(string nodeName = "Start")
{
    if (isRunning)
    {
        Debug.LogWarning("Can't start a dialogue that is already running");
        return;
    }
    isRunning = true;
    dialogue.SetNode(nodeName);
    dialogue.Continue();
}
public void StopDialogue()
{
    dialogue.Stop();
    isRunning = false;
}
```

These methods are very minimal in what they do, they set some flags for state and otherwise just let the dialogue object itself know things have changed.

Replace the `HandleOptions` method with the following:

```csharp
private void HandleOptions(Yarn.OptionSet options)
{
    DialogueOption[] optionSet = new DialogueOption[options.Options.Length];
    for (int i = 0; i < options.Options.Length; i++)
    {
        var line = LineProvider.GetLocalizedLine(options.Options[i].Line);
        var text = Yarn.Dialogue.ExpandSubstitutions(line.RawText, options.Options[i].Line.Substitutions);
        dialogue.LanguageCode = LineProvider.textLanguageCode;
        line.Text = dialogue.ParseMarkup(text);

        optionSet[i] = new DialogueOption
        {
            TextID = options.Options[i].Line.ID,
            DialogueOptionID = options.Options[i].ID,
            Line = line,
            IsAvailable = options.Options[i].IsAvailable,
        };
    }
    OptionsNeedPresentation?.Invoke(optionSet);
}
```

In this method we do a few more steps, we go through each option in the option set and configure them so that other parts of our game can make use of them. We do this by first getting the line inside of the option from our line provider and then we do any necessary substitution of variables inside of the line, and then finally we parse any markup inside of the line. With that done the line is ready, we then make a new `DialogueOption` with that line and other relevant option info, in particular the availability and ID of the option, and then add that to an array. Once we have run this process on every option in the set of options we fire off the event with the array of our configured options for the rest of the game to use.

Replace the `HandleCommand` method with the following:

```csharp
private void HandleCommand(Yarn.Command command)
{
    var elements = Yarn.Unity.DialogueRunner.SplitCommandText(command.Text).ToArray();

    if (elements[0] == "wait")
    {
        if (elements.Length < 2)
        {
            Debug.LogWarning("Asked to wait but given no duration!");
            return;
        }
        float duration = float.Parse(elements[1]);
        if (duration > 0)
        {
            IEnumerator Wait(float time)
            {
                isRunning = false;
                yield return new WaitForSeconds(time);
                isRunning = true;
                Continue();
            }
            StartCoroutine(Wait(duration));
        }
    }
    else
    {
        CommandNeedsHandling?.Invoke(elements);
    }
}
```

When it comes to commands there are two parts, if the command is `wait` we will handle it, otherwise we send it off for other parts of the game to deal with. In this method we split the command up into its constituent parts, we use an existing method to do this so that situations like `<<unlock "room seven">>` are split up into the elements of `unlock` and `room seven`, although we could do this ourselves if we want. Once that is done we check if the command is a wait command and if it is we run a coroutine to wait for the duration, otherwise we fire off our command event to let the rest of the game worry about the command.

Replace the `HandleLine` method with the following:

```csharp
private void HandleLine(Yarn.Line line)
{
    var finalLine = LineProvider.GetLocalizedLine(line);
    var text = Yarn.Dialogue.ExpandSubstitutions(finalLine.RawText, line.Substitutions);
    dialogue.LanguageCode = LineProvider.textLanguageCode;
    finalLine.Text = dialogue.ParseMarkup(text);

    LineNeedsPresentation?.Invoke(finalLine);
}
```

Much like with the options, here we are getting a line from our line provider, performing any substitution, parsing markup and then sending it off. Unlike the options however we only have to do this once as lines come in one at a time.

Finally now we do the three simple events, `HandleNodeStarted`, `HandleNodeEnded`, `HandleDialogueComplete`:

```csharp
private void HandleNodeStarted(string nodeName)
{
    NodeStarted?.Invoke(nodeName);
}
private void HandleNodeEnded(string nodeName)
{
    NodeEnded?.Invoke(nodeName);
}
private void HandleDialogueComplete()
{
    isRunning = false;
    DialogueComplete?.Invoke();
}
```

With these done we have now handled all the events that our runner needs to ensure are handled, all that remains is to implement the `Continue` and `SetSelectedOption` methods. These two will allow us advance the dialogue and choose options, so lets add them now:

```csharp
public void Continue()
{
    if (!isRunning)
    {
        Debug.LogWarning("Can't continue dialogue when we aren't currently running any");
        return;
    }

    dialogue.Continue();
}
public void SetSelectedOption(int optionIndex)
{
    if (!isRunning)
    {
        Debug.LogWarning("Can't select an option when not currently running dialogue");
        return;
    }
    dialogue.SetSelectedOption(optionIndex);
    dialogue.Continue();
}
```

Both of these are similar, they both advance the dialogue itself onto the next event and in the case of `SetSelectedOption` chooses an option first. With that done we are finished with the events and the flow, now we need to setup the runner and dialogue so that they can actually do something with all these events we just handled.

### Configuring the dialogue

Everything done so far has been about the handling and dispatching of events and flow we now need to configure the runner and dialogue class so that it can actually _do_ something. First lets configure the various pieces of the runner itself, add the following code:

```csharp
void Awake()
{
    if (VariableStorage == null)
    {
        VariableStorage = gameObject.AddComponent<InMemoryVariableStorage>();
    }
    dialogue = CreateDialogueInstance();
    dialogue.SetProgram(project.GetProgram());

    if (LineProvider == null)
    {
        LineProvider = gameObject.AddComponent<TextLineProvider>();
    }
    LineProvider.YarnProject = project;
}
```

One method `CreateDialogueInstance` we haven't written yet and will get to in a second, but the rest of this is setting up the pieces the runner will need. In particular we make sure we have a variable storage and line provider and that both are ready to be used, everything else happens in `CreateDialogueInstance` so lets make that now:

```csharp
 private Yarn.Dialogue CreateDialogueInstance()
{
    var dialogue = new Yarn.Dialogue(VariableStorage)
    {
        LogDebugMessage = delegate (string message)
        {
            Debug.Log(message);
        },
        LogErrorMessage = delegate (string message)
        {
            Debug.LogError(message);
        },

        LineHandler = HandleLine,
        CommandHandler = HandleCommand,
        OptionsHandler = HandleOptions,
        NodeStartHandler = HandleNodeStarted,
        NodeCompleteHandler = HandleNodeEnded,
        DialogueCompleteHandler = HandleDialogueComplete,
        PrepareForLinesHandler = PrepareForLines
    };
    return dialogue;
}
```

The dialogue class being configured here is structurally very similar to our own runner, we have hooks that are run when important events happen. Its realistically the Dialogue class that does most of the heavy lifting, we are acting as a dispatching and Unity friendly window into the Dialogue. With that finished our custom dialogue runner is done, time to hook it up to something to make it dance.

## Building the new Views

The existing views Yarn Spinner provides assume that you are using the callback model the runner has, ours no longer does that so they are incompatible. So we will make some new ones, based off the originals but to handle our custom runners approach instead of the original. Before going any further its worth saying we could modify the runner so that it mimics the callback model and we could reuse the existing views, we chose not to do that because it isn't really a great example of taking control over the dialogue if you end up just rebuilding the exact same (or very similar) thing.

### Line View

We'll get started with the line view first, and to speed things up we are gonna be reusing most of the code from the existing `LineView`.

1. Back inside Unity create a new C# file
2. Name it `MinimalLineView`
3. Add the following code:

```csharp
using System;
using System.Collections;
using UnityEngine;
using TMPro;
using UnityEngine.UI;
using Yarn.Unity;

public class MinimalLineView : MonoBehaviour
{
    [SerializeField] internal CanvasGroup canvasGroup;

    [SerializeField] internal bool useFadeEffect = true;

    [SerializeField]
    [Min(0)]
    internal float fadeInTime = 0.25f;

    [SerializeField]
    [Min(0)]
    internal float fadeOutTime = 0.05f;

    [SerializeField] internal TextMeshProUGUI lineText = null;

    [SerializeField] internal bool showCharacterNameInLineView = true;

    [SerializeField] internal TextMeshProUGUI characterNameText = null;

    [SerializeField] internal bool useTypewriterEffect = false;

    [SerializeField]
    [Min(0)]
    internal float typewriterEffectSpeed = 0f;

    [SerializeField] internal GameObject continueButton = null;

    [SerializeField]
    [Min(0)]
    internal float holdTime = 1f;

    LocalizedLine currentLine = null;

    Effects.CoroutineInterruptToken currentStopToken = new Effects.CoroutineInterruptToken();

    private MinimalDialogueRunner runner;

    private void Awake()
    {
        canvasGroup.alpha = 0;
        canvasGroup.blocksRaycasts = false;
    }
    void Start() { runner = FindObjectOfType<MinimalDialogueRunner>(); }
    private void Reset() { canvasGroup = GetComponentInParent<CanvasGroup>(); }

    public void DismissLine()
    {
        currentLine = null;

        StartCoroutine(DismissLineInternal());
    }

    private IEnumerator DismissLineInternal()
    {
        var interactable = canvasGroup.interactable;
        canvasGroup.interactable = false;

        if (useFadeEffect)
        {
            yield return StartCoroutine(Effects.FadeAlpha(canvasGroup, 1, 0, fadeOutTime, currentStopToken));
            currentStopToken.Complete();
        }

        canvasGroup.alpha = 0;
        canvasGroup.blocksRaycasts = false;
        canvasGroup.interactable = interactable;
        runner.Continue();
    }

    public void RunLine(LocalizedLine dialogueLine)
    {
        StopAllCoroutines();
        StartCoroutine(RunLineInternal(dialogueLine));
    }

    private IEnumerator RunLineInternal(LocalizedLine dialogueLine)
    {
        IEnumerator PresentLine()
        {
            lineText.gameObject.SetActive(true);
            canvasGroup.gameObject.SetActive(true);

            if (continueButton != null)
            {
                continueButton.SetActive(false);
            }

            if (characterNameText != null)
            {
                characterNameText.text = dialogueLine.CharacterName;
                lineText.text = dialogueLine.TextWithoutCharacterName.Text;
            }
            else
            {
                if (showCharacterNameInLineView)
                {
                    lineText.text = dialogueLine.Text.Text;
                }
                else
                {
                    lineText.text = dialogueLine.TextWithoutCharacterName.Text;
                }
            }

            if (useTypewriterEffect)
            {
                lineText.maxVisibleCharacters = 0;
            }
            else
            {
                lineText.maxVisibleCharacters = int.MaxValue;
            }

            if (useFadeEffect)
            {
                yield return StartCoroutine(Effects.FadeAlpha(canvasGroup, 0, 1, fadeInTime, currentStopToken));
                if (currentStopToken.WasInterrupted) {
                    yield break;
                }
            }

            if (useTypewriterEffect)
            {
                canvasGroup.alpha = 1f;
                canvasGroup.interactable = true;
                canvasGroup.blocksRaycasts = true;
                yield return StartCoroutine(
                    Effects.Typewriter(
                        lineText,
                        typewriterEffectSpeed,
                        null,
                        currentStopToken
                    )
                );
                if (currentStopToken.WasInterrupted) {
                    yield break;
                }
            }
        }
        currentLine = dialogueLine;

        yield return StartCoroutine(PresentLine());

        currentStopToken.Complete();
        lineText.maxVisibleCharacters = int.MaxValue;
        canvasGroup.alpha = 1f;
        canvasGroup.blocksRaycasts = true;

        if (holdTime > 0)
        {
            yield return new WaitForSeconds(holdTime);
        }
        if (continueButton != null)
        {
            continueButton.SetActive(true);
        }
    }

    public void OnContinueClicked()
    {
        if (currentLine == null)
        {
            return;
        }
        DismissLine();
    }
}
```

Most of the code here is unchanged from the original. The main differences is we are no longer derived from the `DialogueViewBase` class but are just normal gameobjects and all the method signatures for handling the dialogue events no longer have a callback method. Now when they have done their stuff they just call `Continue` on our runner.

### Options View

Much like with our line view our options view will also be mostly copy-pasted from the existing `OptionListView` class and modified as in. We will still be using the `OptionView` class and default prefab just to save time, so this will require a little bit of emulating some callbacks so that works, but won't be too much.

1. Create a new C# file
2. Name it `MinimalOptionsView`
3. Add the following code:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Yarn.Unity;
using TMPro;

public class MinimalOptionsView : MonoBehaviour
{
    [SerializeField] CanvasGroup canvasGroup;

    [SerializeField] OptionView optionViewPrefab;

    [SerializeField] TextMeshProUGUI lastLineText;

    [SerializeField] float fadeTime = 0.1f;

    [SerializeField] bool showUnavailableOptions = false;

    List<OptionView> optionViews = new List<OptionView>();

    LocalizedLine lastSeenLine;

    private MinimalDialogueRunner runner;

    public void Start()
    {
        runner = FindObjectOfType<MinimalDialogueRunner>();

        canvasGroup.alpha = 0;
        canvasGroup.interactable = false;
        canvasGroup.blocksRaycasts = false;
    }

    public void Reset() { canvasGroup = GetComponentInParent<CanvasGroup>(); }

    public void RunLine(LocalizedLine dialogueLine) { lastSeenLine = dialogueLine; }

    public void RunOptions(DialogueOption[] options)
    {
        System.Action<Yarn.Unity.DialogueOption> onOptionSelected = delegate(DialogueOption selectedOption)
        {
            StartCoroutine(OptionViewWasSelectedInternal(selectedOption));
            IEnumerator OptionViewWasSelectedInternal(DialogueOption selectedOption)
            {
                yield return StartCoroutine(Yarn.Unity.Effects.FadeAlpha(canvasGroup, 1, 0, fadeTime));
                runner.SetSelectedOption(selectedOption.DialogueOptionID);
            }
        };

        foreach (var optionView in optionViews) { optionView.gameObject.SetActive(false); }

        while (options.Length > optionViews.Count)
        {
            var optionView = CreateNewOptionView(onOptionSelected);
            optionView.gameObject.SetActive(false);
        }

        int optionViewsCreated = 0;

        for (int i = 0; i < options.Length; i++)
        {
            var optionView = optionViews[i];
            var option = options[i];

            if (option.IsAvailable == false && showUnavailableOptions == false) { continue; }

            optionView.gameObject.SetActive(true);

            optionView.Option = option;
            optionView.OnOptionSelected = onOptionSelected;

            if (optionViewsCreated == 0)
            {
                optionView.Select();
            }

            optionViewsCreated += 1;
        }

        if (lastLineText != null)
        {
            if (lastSeenLine != null)
            {
                lastLineText.gameObject.SetActive(true);
                lastLineText.text = lastSeenLine.Text.Text;
            }
            else
            {
                lastLineText.gameObject.SetActive(false);
            }
        }

        StartCoroutine(Effects.FadeAlpha(canvasGroup, 0, 1, fadeTime));

        OptionView CreateNewOptionView(System.Action<Yarn.Unity.DialogueOption> callback)
        {
            var optionView = Instantiate(optionViewPrefab);
            optionView.transform.SetParent(transform, false);
            optionView.transform.SetAsLastSibling();

            optionView.OnOptionSelected = callback;
            optionViews.Add(optionView);

            return optionView;
        }
    }
}
```

Again this is almost identical to the original code, just with some tweaks here and there. Of interest is the `RunLine` method, when this is hooked up later it will let us get access to the line and we don't have to do anything to advance the dialogue because in the line view that is doing that side of it.

### And everything else

So our views are ready, but we still have a lot of other events we haven't handled and we also don't currently have a way to _start_ the dialogue, let's fix that.

. Make a new C# file . Name it `DialogueSupportComponent` . Add the following code:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class DialogueSupportComponent : MonoBehaviour
{
    MinimalDialogueRunner runner;
    void Start() { runner = FindObjectOfType<MinimalDialogueRunner>(); }

    void Update()
    {
        if (Input.GetKeyUp(KeyCode.Space))
        {
            if (!runner.isRunning)
            {
                runner.StartDialogue();
            }
        }
    }

    public void HandleCommand(string[] commandText)
    {
        Debug.Log($"Received a command: {commandText[0]}");
        runner.Continue();
    }
    public void LogNodeStarted(string node) { Debug.Log($"entered node {node}"); }
    public void LogNodeEnded(string node) { Debug.Log($"exited node {node}"); }
    public void LogDialogueEnded() { Debug.Log("Dialogue has finished"); }
}
```

This class basically just logs every other event, in a more complete scenario you might have to do more but for us just logging is fine. We also have a very crude means of starting the dialogue now, by pressing the Spacebar.

## Hooking it all up in the scene

Now for the last little bits and pieces, we need to hook everything up in the scene, to speed things up we are gonna be using the Dialogue System prefab and reworking it to use our components.

1. Add a Dialogue System Prefab into the scene
2. Select the prefab in the hierarchy
3. In the Inspector unpack the prefab
4. Remove the Dialogue Runner component from the prefab and add in our Minimal Dialogue Runner component in its place
5. Add a Dialogue Support Component to the prefab
6. Expand the Prefab, go into the Canvas -> Line View
7. Remove the Line View component
8. Add our Minimal Line View component in its place
9. Hook up the Line Text, Character Name Text, and Continue Button fields to their respective UI elements in the UI
10. Select the Options List View inside of Canvas -> Options List View
11. Remove the Options List View
12. Add our Minimal Options View in its place
13. Hook up the Last Line Text, and Options View Prefab

Now the UI and components are in their right place time to connect everything into our runner.

1. Select the Minimal Runner component in the hierarchy
2. Connect the Command Needs Handling event up to the Dialogue Support Component's `HandleCommand` method
3. Connect the Node Started event up to the Dialogue Support Component's `LogNodeStarted` method
4. Connect the Node Ended event up to the Dialogue Support Component's `LogNodeEnded` method
5. Connect the Dialogue Complete event up to the Dialogue Support Component's `LogDialogueComplete` method
6. Connect the Options Need Presentation event up to the Minimal Options View's `RunOptions` method
7. Connect the Line Needs Presentation event up to the Minimal Options View's and Minimal Line View's `RunLine` method

[Test link](broken-reference); if you see this, you saw us doing stuff behind the scenes!

Our runner is now fully hooked up, lets give it a go.

1. Create a new Yarn file
2. Add some content
3. Create a Yarn Project
4. Hook your yarn file up to the project
5. Hook the project up to the Dialogue Runner
6. Start the scene
7. Press the Spacebar
8. Sit back and enjoy your story powered by your runner

## The End?

We've done an awful lot in this guide, created new runners and UI to accompany them, and as part of it taken a deeper look into how Yarn Spinner itself works. There is still a lot more to do before you could ever use this runner in an actual production game, for a start it doesn't set up default variables, but this is the basis of a much larger world. Hopefully now if you find yourself wanting a different flow to your architecture or am needing more control over the process of handling your Yarn you will have the tools needed to do it yourself.
