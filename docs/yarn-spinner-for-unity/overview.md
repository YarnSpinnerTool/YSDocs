---
description: Use Yarn Spinner Scripts in Unity games, using Yarn Spinner for Unity.
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# ⭐ First Steps + FAQ

**Yarn Spinner for Unity** is the set of components and scripts that make Yarn Spinner work inside a Unity project.

In this section, you’ll learn how to install, set up, and work with Yarn Spinner for Unity.

{% hint style="danger" %}
Yarn Spinner for Unity 3 is compatible with Unity version 2022.3 and newer. If you need to use an older version of Unity, use Yarn Spinner 2.
{% endhint %}

If you're here to get started, dive into the [installation-and-setup](installation-and-setup/ "mention") page.

***

## FAQ for Yarn Spinner for Unity

### Text

### How do I style text? How do I make some words bold, italic, colorful, etc?

Yarn Spinner doesn't do text rendering, you have to use existing Unity systems like TextMeshPro. Fortunately, TMP supports HTML-like rich text tags. See the [TextMeshPro: Rich Text docs](https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/RichText.html).

```
Alice: This text is <b>bold!</b>
Bob: This text is <color=red>red!</color>

// NOTE: '#' is a special character in Yarn, used for line tags.
// To use a HTML color hex code, you must "escape" the "#" character with a "\"
Carol: Wow I'm <color=\#ff00ff>purple</color>!
```

However, this bespoke approach is impractical for longer scripts or bigger projects. We recommend using TextMeshPro's Style Sheets, which make it much easier to write consistently styled text. See the [TextMeshPro: Style Sheets docs](https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/StyleSheets.html).

### How do I animate wavy text, like in Night In The Woods?

Yarn Spinner doesn't handle text rendering. You'll need a separate wavy text system, like [Text Animator](https://assetstore.unity.com/packages/tools/gui/text-animator-for-unity-158707).

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

Note that _YS only processes the text data_. You must still code the actual markup effect yourself. See [Markup](../write-yarn-scripts/editing-with-vs-code/markup.md).

## Variables

### How do I print the value of a variable in dialogue?

Wrap the variable (or any expression) in curly braces (`{`, `}`) to evaluate and output it. For more info, see [Variables](../write-yarn-scripts/logic-and-variables/).

```
<<set $variableName to "a string value">>
The value of variableName is {$variableName}.
// This will appear as "The value of variableName is a string value."
```

### How do I read / write Yarn variables from a C# script?

To read Yarn variables from C#, use [`VariableStorageBehaviour.TryGetValue<T>()`](broken-reference). To write Yarn variables from C#, use [`VariableStorageBehaviour.SetValue()`](broken-reference).

{% hint style="info" %}
Don't forget the `$` when writing the variable's name!
{% endhint %}

```csharp
variableStorage = GameObject.FindObjectOfType<InMemoryVariableStorage>();
float testVariable;
variableStorage.TryGetValue("$testVariable", out testVariable);
variableStorage.SetValue("$testVariable", testVariable + 1);
```

### How do I read / write C# variables from a Yarn script?

To read and write C# variables from Yarn, you must first code [Yarn Functions and Commands](creating-commands-functions.md) in C#.

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

{% hint style="info" %}
If you're using Unity 2021.1 or earlier, you'll need to ask Yarn Spinner to update some code in your project that registers these C# methods as Yarn functions. To do this, open the Window menu, and choose Yarn Spinner -> Update Yarn Commands.

You don't need to do this if you're using Unity 2021.2 or later.
{% endhint %}

### How do I 'sync' variables between Yarn and C#?

See the previous answers on working with variables. But we recommend avoiding any "sync" pattern, because then you'll have to track and maintain the same data in two different places. Programmers usually prefer a ["single source of truth"](https://en.wikipedia.org/wiki/Single_source_of_truth). Data should live in only one place. Variables should either live in Yarn or live in C#, and not in both.

### How do I load and save data / variables / dialogue state? (Like for a save game system)

To save the current node, save the value of [`DialogueRunner.CurrentNodeName`](broken-reference) somewhere, e.g. to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html). Then to restore it, call [`DialogueRunner.StartDialogue()`](broken-reference) and pass in the saved node name.

To save variables, see [`DialogueRunner.SaveStateToPersistentStorage()`](broken-reference). Then to load variables, call [`DialogueRunner.LoadStateFromPersistentStorage()`](broken-reference). These methods use Unity's built-in JSON utility to serialize a dictionary of variables to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html).

For custom save systems, create your own [variable storage](../yarn-spinner-for-other-engines/godot/components/variable-storage/) by subclassing VariableStorageBehaviour and implementing its methods. Study [InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/InMemoryVariableStorage.cs) as an example. For more info, see [Guide: Yarn Variables and Variable Storage](broken-reference).

It is not currently possible to save or restore the specific line that the dialogue is running.

## Control flow

### How do I jump to a specific node? How do I switch nodes while dialogue is running?

To jump to a node from Yarn, use `<<jump (nodeName)>>`. See [Nodes, Lines, and Options](../write-yarn-scripts/lines-nodes-and-options.md).

To jump to a node with C#, just call [`DialogueRunner.StartDialogue()`](broken-reference), even if there's already dialogue running.

### How do I jump to a specific line in a node?

Jumping to a specific line in a node is currently not supported. Instead, [jump to the start of a node](overview.md#how-do-i-jump-to-a-specific-node-how-do-i-switch-nodes-while-dialogue-is-running).

## Interaction / UI

### How do I continue dialogue with key/button press instead of clicking the continue button?

In most cases, use the [Dialogue Advance Input](components/dialogue-view/dialogue-advance-input.md).

For more control, call [`UserRequestedViewAdvancement()`](broken-reference) on a Dialogue View, or [`OnContinuedClicked()`](broken-reference) on a Line View. See [Creating Custom Dialogue Views](components/dialogue-view/custom-dialogue-views.md).

### How do I show the last line of text when options are shown? How do I skip the last line of text before a set of options?

Yarn Spinner automatically adds a `#lastline` tag to a line when the next step is a set of options. Create a [Custom Dialogue View](components/dialogue-view/custom-dialogue-views.md) that uses [`YarnProject.lineMetadata.GetMetadata()`](broken-reference) to check for "lastline" and perform the behavior you want.

### How do I show the character name / portrait? How do I customize dialogue display?

To display _anything_ in Yarn Spinner, use a [Dialogue View](../using-yarnspinner-with-unity/components/dialogue-view.md) component. [Line View](broken-reference) for dialogue, [Options List View](broken-reference) for choices.

Most projects will need custom views. We recommend a modular architecture where each UI element has its own LineView component. For example, a nameplate bubble has a [Dialogue Character Name View](../api/csharp/yarn.unity/yarn.unity.dialoguecharacternameview) that displays [`LocalizedLine.CharacterName`](broken-reference), while the dialogue text window is another Line View that displays [`LocalizedLine.TextWithoutCharacterName`](broken-reference). See [Creating Custom Dialogue Views](components/dialogue-view/custom-dialogue-views.md).

For a working example, see the "Visual Novel" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "Visual Novel" and import it.) Specifically, see [VNManager.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/VisualNovel/Scripts/VNManager.cs) which inherits from DialogueViewBase, and changes the character name window background color (among other effects) based on the character name.

### How do I make the Line View's Typewriter effect pause on punctuation?

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

Write input code to detect clicking / tapping, then call `DialogueRunner.StartDialogue()`.

The example tutorial [NPC Dialogue Game](broken-reference) can walk you through this step-by-step.

### How do I play a Yarn node when I approach an object and press a button? (RPG-like talking to NPCs)

This implementation will vary for every game, so we purposely do not attempt to design a one-size-fits-all generic NPC system. Here's some example pseudo-code to make your own:

```
if (player presses SPACE)
    then find the nearest NPC
    get that NPC's dialogue node name
    call DialogueRunner.StartDialogue() with the NPC's dialogue node
    disable player movement
```

For a working example, see the "Space" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "Space" and import it.) Specifically, see [PlayerCharacter.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/Space/Scripts/PlayerCharacter.cs) for how to search for nearby NPCs from a list.

### How do I position a speech bubble above an NPC's head, like in A Short Hike?

The math / code is a little complicated. Calculate the NPC's on-screen position, then convert this screen position to UI canvas space, and reposition the dialogue bubble.

For a working example, see the "3D" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "3D" and import it.) Specfically, see [YarnCharacterView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/3D/Scripts/YarnCharacterView.cs) which has a method `WorldToAnchoredPosition()` that does a lot of this UI positioning math.

### How do I implement a resizing dialogue bubble / SMS messaging interface?

This is more about Unity UI rather than Yarn Spinner. For a working example, see the "Phone Chat" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "Phone Chat" and import it.)

To make a resizing dialogue bubble that automatically fits text, you will need a complex UI setup. Study the UI game objects and components in the sample scene. For more context about how it works, see [this Unity UI Layout Groups explainer by Hallgrim Games](https://www.hallgrimgames.com/blog/2018/10/16/unity-layout-groups-explained).

### How do I get text from a Text Input field into my Yarn story?

This mainly involves Unity UI, and assumes that your project already has a system where a player can input text like a TMPro Input Field component. If the player input needs to happen in the middle of dialogue execution then you can trigger it with a Yarn Command, using a coroutine to wait for the player input if needed.

Once you have the player input value, you can store it in a C# variable and access it through a Yarn function, or store that value in a Yarn story variable. [FAQs for how to access variables in Yarn and YarnSpinner are here](overview.md#variables).

## System

### How do I generate a Yarn Project at runtime? How do I load/compile Yarn scripts at runtime?

The intended workflow is to generate and compile Yarn Projects at editor time, not runtime. See [Yarn Projects](yarn-projects.md).

{% hint style="info" %}
Compiling a Yarn script at run-time is more complex than it first appears, because it often interacts with the very specific needs of your game, and we can't provide a one-size-fits-all approach to it. If you want to implement run-time loading in your own game, the place to start looking is the API documentation for the [Yarn.Compiler](broken-reference) namespace. Please note that this is not something that we encourage people who are new to Yarn Spinner to do!
{% endhint %}

### How many Yarn files should I have? Can my entire game be in one project or script? Or one project per scene? Is my project or file too big?

There is no real technical limit on the number of Yarn scripts or the size of Yarn Projects. You decide how to organize your data, and every project has different needs. Some factors to consider:

* **Simplicity**. Putting everything into one big script file or one big project file is simpler sometimes.
* **Ease of writing**. Writers may prefer to think in terms of one file per scene, one file per chapter.
* **Localization**. 1 Yarn Project = 1 CSV spreadsheet per language. When translating, it is usually easier to work with fewer files, rather than fragmenting the translation across many files. As a workaround for games that need multiple Yarn Projects, you may prefer to create a single editor-only Yarn Project that's just for generating string files and translations. See [Localizations and Assets](assets-and-localization/).

### I'm seeing crashes on startup in my WebGL / iOS / Android / IL2CPP project.

A crash bug exists in versions of Yarn Spinner earlier than 2.3 for these platforms. If you're able to upgrade your version of Yarn Spinner, the best fix is to upgrade to the most recent version of Yarn Spinner.

If you can't upgrade your version of Yarn Spinner, a workaround for this issue is to open the Build Settings window in Unity, and set the "IL2CPP Code Generation" setting to "Faster (smaller) builds."

## Localization

### How do I fetch any Yarn localized string in C#?

Some devs use YS to manage all in-game localized text, like UI strings. This use isn't intended, but it's possible. Manually create a Yarn.Line struct, set the line ID (see [Localization](assets-and-localization/)), and then pass the struct into [`GetLocalizedLine()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.lineproviderbehaviour/yarn.unity.lineproviderbehaviour.getlocalizedline).

```csharp
Yarn.Line targetLine = new Yarn.Line();
targetLine.ID = "line:lineid"; // replace 'lineid' with the actual line ID
LocalizedLine outputLine = LineProvider.GetLocalizedLine(targetLine);
Debug.Log(outputLine.Text.Text);

```

## Other

### How do I credit Yarn Spinner in my game?

Please visit the [Crediting Yarn Spinner page](../branding.md) for more information. Thanks for thinking of us!
