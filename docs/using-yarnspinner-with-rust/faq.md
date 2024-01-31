---
description: Common questions and solutions for using Yarn Spinner in Rust using Bevy.
---

# 💡 Frequently Asked Questions / "How Do I...?"

## Text

### How do I style text? How do I make some words bold, italic, colorful, etc?

Yarn Spinner doesn't do text rendering, you have to use existing Bevy plugins.

### How do I animate wavy text, like in Night In The Woods?

Yarn Spinner doesn't handle text rendering. You'll need a separate wavy text plugin.

### How do I use Yarn Markup?

Markup lets you mark a range of text (words, phrases) in a generic way, for whatever use. You could use it to style text, add sentence markers, make clickable words, etc.

```
// Yarn script example of custom "wavy text" markup.
Oh, [wave]hello[/wave] there!

// After compiling, text will look like: "Oh, hello there!"
// And then the resulting markup data will look like:
// - name: "wave"
// - position: 4
// - length: 5
```

Note that _YS only processes the text data_. You must still code the actual markup effect yourself. See [Markup](../getting-started/writing-in-yarn/markup.md).

## Variables

### How do I print the value of a variable in dialogue?

Wrap the variable (or any expression) in curly braces (`{`, `}`) to evaluate and output it. For more info, see [Variables](../getting-started/writing-in-yarn/logic-and-variables.md).

```
<<set $variableName to "a string value">>
The value of variableName is {$variableName}.
// This will appear as "The value of variableName is a string value."
```

### How do I read / write Yarn variables from Rust?
TODO
To read Yarn variables from C#, use [`VariableStorageBehaviour.TryGetValue<T>()`](../api/csharp/yarn.ivariablestorage.trygetvalue.md). To write Yarn variables from C#, use [`VariableStorageBehaviour.SetValue()`](../api/csharp/yarn.ivariablestorage.setvalue-1.md).

{% hint style="info" %}
Don't forget the `$` when writing the variable's name!
{% endhint %}

```csharp
variableStorage = GameObject.FindObjectOfType<InMemoryVariableStorage>();
float testVariable;
variableStorage.TryGetValue("$testVariable", out testVariable);
variableStorage.SetValue("$testVariable", testVariable + 1);
```

### How do I read / write Rust variables from a Yarn script?
TODO
To read and write C# variables from Yarn, you must first code [Yarn Functions and Commands](creating-commands-functions/creating-commands.md) in Rust.
TODO RUST
```csharp
static int myNumber = 10;

// note: all Yarn Functions must be static
[YarnFunction("getMyNumber")]
public static int GetMyNumber() { 
    return myNumber; 
}

// Yarb Commands can be static or non-static
[YarnCommand("setMyNumber")]
public static void SetMyNumber(int newNumber) { 
    myNumber = newNumber;
}
```

Then call the functions and commands in Yarn:

```
My number is { getMyNumber() }!
<<setMyNumber 999>>
But now it's { getMyNumber() }!
```


### How do I 'sync' variables between Yarn and C#?

See the previous answers on working with variables. But we recommend avoiding any "sync" pattern, because then you'll have to track and maintain the same data in two different places. Programmers usually prefer a ["single source of truth"](https://en.wikipedia.org/wiki/Single\_source\_of\_truth). Data should live in only one place. Variables should either live in Yarn or live in Rust, and not in both.

### How do I load and save data / variables / dialogue state? (Like for a save game system)
TODO
To save the current node, save the value of [`DialogueRunner.CurrentNodeName`](../api/csharp/yarn.unity.dialoguerunner.currentnodename.md) somewhere, e.g. to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html). Then to restore it, call [`DialogueRunner.StartDialogue()`](../api/csharp/yarn.unity.dialoguerunner.startdialogue.md) and pass in the saved node name.

To save variables, see [`DialogueRunner.SaveStateToPersistentStorage()`](../api/csharp/yarn.unity.dialoguerunner.savestatetopersistentstorage.md). Then to load variables, call [`DialogueRunner.LoadStateFromPersistentStorage()`](../api/csharp/yarn.unity.dialoguerunner.loadstatefrompersistentstorage.md). These methods use Unity's built-in JSON utility to serialize a dictionary of variables to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html).

For custom save systems, create your own [variable storage](components/variable-storage/) by subclassing VariableStorageBehaviour and implementing its methods. Study [InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/InMemoryVariableStorage.cs) as an example. For more info, see [Guide: Yarn Variables and Variable Storage](../guides/yarn-variables-and-variable-storage.md).

It is not currently possible to save or restore the specific line that the dialogue is running.

## Control flow

### How do I jump to a specific node? How do I switch nodes while dialogue is running?

To jump to a node from Yarn, use `<<jump (nodeName)>>`. See [Nodes, Lines, and Options](../getting-started/writing-in-yarn/lines-nodes-and-options.md).

To jump to a node with Rust, just call [`DialogueRunner.start_node("nodeName")`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/struct.DialogueRunner.html#method.start_node), even if there's already dialogue running.

### How do I jump to a specific line in a node?

Jumping to a specific line in a node is currently not supported. Instead, [jump to the start of a node](faq.md#how-do-i-jump-to-a-specific-node-how-do-i-switch-nodes-while-dialogue-is-running).

## Interaction / UI

### How do I continue dialogue with key/button press instead of clicking the continue button?
TODO
In most cases, use the [Dialogue Advance Input](components/dialogue-view/dialogue-advance-input.md).

For more control, call [`UserRequestedViewAdvancement()`](../api/csharp/yarn.unity.lineview.userrequestedviewadvancement.md) on a Dialogue View, or [`OnContinuedClicked()`](../api/csharp/yarn.unity.lineview.oncontinueclicked.md) on a Line View. See [Creating Custom Dialogue Views](components/dialogue-view/custom-dialogue-views.md).

### How do I show the last line of text when options are shown? How do I skip the last line of text before a set of options?
TODO
Yarn Spinner automatically adds a `#lastline` tag to a line when the next step is a set of options. Create a [Custom Dialogue View](components/dialogue-view/custom-dialogue-views.md) that uses [`YarnProject.lineMetadata.GetMetadata()`](../api/csharp/yarn.unity.linemetadata.getmetadata.md) to check for "lastline" and perform the behavior you want.

### How do I show the character name / portrait? How do I customize dialogue display?
TODO
To display _anything_ in Yarn Spinner, use a [Dialogue View](components/dialogue-view.md) component. [Line View](components/dialogue-view/line-view.md) for dialogue, [Options List View](components/dialogue-view/options-list-view.md) for choices.

Most projects will need custom views. We recommend a modular architecture where each UI element has its own LineView component. For example, a nameplate bubble has a [Dialogue Character Name View](../api/csharp/yarn.unity/yarn.unity.dialoguecharacternameview) that displays [`LocalizedLine.CharacterName`](../api/csharp/yarn.unity.localizedline.charactername.md), while the dialogue text window is another Line View that displays [`LocalizedLine.TextWithoutCharacterName`](../api/csharp/yarn.unity.localizedline.textwithoutcharactername.md). See [Creating Custom Dialogue Views](components/dialogue-view/custom-dialogue-views.md).

### How do I make the Line View's Typewriter effect pause on punctuation?
TODO
Create a custom dialogue view with a custom effect based on `Typewriter()` (see [Effects.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/Views/Effects.cs)) to detect the next text character and pause accordingly.

```csharp
// in your custom Typewriter effect, replace the "while (accumulator >= secondsPerLetter)..." block with this one:
while (accumulator >= secondsPerLetter) {
   text.maxVisibleCharacters += 1;
   onCharacterTyped?.Invoke();
   accumulator -= secondsPerLetter;

   // Don't pause on the last character
   if (text.maxVisibleCharacters >= characterCount) continue;

   // Extra pause on punctuation
   var nextChar = text.text[text.maxVisibleCharacters - 1];
   if (nextChar.Equals('.') || nextChar.Equals(',') || nextChar.Equals('?') || nextChar.Equals('!')) {
       yield return new WaitForSeconds(0.3f);
   }

   accumulator += Time.deltaTime;
   yield return null;
}
```

### How do I play a Yarn node when I click / tap on an object?

Write input code to detect clicking / tapping, then call [`DialogueRunner.start_node("your-node-name")`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/struct.DialogueRunner.html#method.start_node).

### How do I play a Yarn node when I approach an object and press a button? (RPG-like talking to NPCs)

This implementation will vary for every game, so we purposely do not attempt to design a one-size-fits-all generic NPC system. Here's some example pseudo-code to make your own:

```
if (player presses SPACE)
    then find the nearest NPC
    get that NPC's dialogue node name
    call DialogueRunner.StartDialogue() with the NPC's dialogue node
    disable player movement
```

### How do I position a speech bubble above an NPC's head, like in A Short Hike?

The math / code is a little complicated. Calculate the NPC's on-screen position, then convert this screen position to UI canvas space, and reposition the dialogue bubble.

### How do I implement a resizing dialogue bubble / SMS messaging interface?
TODO
This is more about Unity UI rather than Yarn Spinner. For a working example, see the "Phone Chat" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "Phone Chat" and import it.)

To make a resizing dialogue bubble that automatically fits text, you will need a complex UI setup. Study the UI game objects and components in the sample scene. For more context about how it works, see [this Unity UI Layout Groups explainer by Hallgrim Games](https://www.hallgrimgames.com/blog/2018/10/16/unity-layout-groups-explained).

### How do I get text from a Text Input field into my Yarn story?
TODO
This mainly involves Unity UI, and assumes that your project already has a system where a player can input text like a TMPro Input Field component. If the player input needs to happen in the middle of dialogue execution then you can trigger it with a Yarn Command, using a coroutine to wait for the player input if needed.

Once you have the player input value, you can store it in a C# variable and access it through a Yarn function, or store that value in a Yarn story variable. [FAQs for how to access variables in Yarn and YarnSpinner are here](faq.md#variables).

## System

### How many Yarn files should I have? Can my entire game be in one project or script? Or one project per scene? Is my project or file too big?

There is no real technical limit on the number of Yarn scripts or the size of Yarn Projects. You decide how to organize your data, and every project has different needs. Some factors to consider:

* **Simplicity**. Putting everything into one big script file or one big project file is simpler sometimes.
* **Ease of writing**. Writers may prefer to think in terms of one file per scene, one file per chapter.
* **Localization**. 1 Yarn Project = 1 CSV spreadsheet per language. When translating, it is usually easier to work with fewer files, rather than fragmenting the translation across many files. As a workaround for games that need multiple Yarn Projects, you may prefer to create a single editor-only Yarn Project that's just for generating string files and translations. See [Localizations](localisation.md).

## Localization

### How do I fetch any Yarn localized string in C#?
TODO
Some devs use YS to manage all in-game localized text, like UI strings. This use isn't intended, but it's possible. Manually create a Yarn.Line struct, set the line ID (see [Localization](assets-and-localization/)), and then pass the struct into [`GetLocalizedLine()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.lineproviderbehaviour/yarn.unity.lineproviderbehaviour.getlocalizedline).

```csharp
Yarn.Line targetLine = new Yarn.Line();
targetLine.ID = "line:lineid"; // replace 'lineid' with the actual line ID
LocalizedLine outputLine = LineProvider.GetLocalizedLine(targetLine);
Debug.Log(outputLine.Text.Text);

```

## Other

### How do I credit Yarn Spinner in my game?

Please visit the [Crediting Yarn Spinner page](../about/branding.md) for more information. Thanks for thinking of us!
