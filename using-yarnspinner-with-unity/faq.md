---
description: Common questions and solutions for using Yarn Spinner in Unity.
---

# 💡 FAQ / How Do I... ?

## Text

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

Note that _YS only processes the text data_. You must still code the actual markup effect yourself. See [Markup](../getting-started/writing-in-yarn/markup.md).

## Variables

### How do I print the value of a variable in dialogue?

Wrap the variable (or any expression) in curly braces (`{`, `}`) to evaluate and output it. For more info, see [Variables](../getting-started/writing-in-yarn/logic-and-variables.md).

```
<<set $variableName to "a string value">>
The value of variableName is {$variableName}.
// This will appear as "The value of variableName is a string value."
```

### How do I read / write Yarn variables from a C# script?

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

To save the current node, save the value of [`DialogueRunner.CurrentNodeName`](../api/csharp/yarn.unity.dialoguerunner.currentnodename.md) somewhere, e.g. to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html). Then to restore it, call [`DialogueRunner.StartDialogue()`](../api/csharp/yarn.unity.dialoguerunner.startdialogue.md) and pass in the saved node name.

To save variables, see [`DialogueRunner.SaveStateToPlayerPrefs()`](../api/csharp/yarn.unity.dialoguerunner.savestatetoplayerprefs.md). Then to load variables, call [`DialogueRunner.LoadStateFromPlayerPrefs()`](../api/csharp/yarn.unity.dialoguerunner.loadstatefromplayerprefs.md). These methods use Unity's built-in JSON utility to serialize a dictionary of variables to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html).

For custom save systems, create your own [variable storage](components/variable-storage/) by subclassing VariableStorageBehaviour and implementing its methods. Study [InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/InMemoryVariableStorage.cs) as an example. For more info, see [Guide: Yarn Variables and Variable Storage](../guides/yarn-variables-and-variable-storage.md).

It is not currently possible to save or restore the specific line that the dialogue is running. 

## Control flow

### How do I jump to a specific node? How do I switch nodes while dialogue is running?

To jump to a node from Yarn, use `<<jump (nodeName)>>`. See [Nodes, Lines, and Options](../getting-started/writing-in-yarn/lines-nodes-and-options.md).

To jump to a node with C#, just call [`DialogueRunner.StartDialogue()`](../api/csharp/yarn.unity.dialoguerunner.startdialogue.md), even if there's already dialogue running.

### How do I jump to a specific line in a node?

Jumping to a specific line in a node is currently not supported. Instead, [jump to the start of a node](#how-do-i-jump-to-a-specific-node-how-do-i-switch-nodes-while-dialogue-is-running).

## Interaction / UI

### How do I continue dialogue with key/button press instead of clicking the continue button?

In most cases, use the [Dialogue Advance Input](components/dialogue-view/dialogue-advance-input.md). 

For more control, call [`UserRequestedViewAdvancement()`](../api/csharp/yarn.unity.lineview.userrequestedviewadvancement.md) on a Dialogue View, or [`OnContinuedClicked()`](../api/csharp/yarn.unity.lineview.oncontinueclicked.md) on a Line View. See [Creating Custom Dialogue Views](components/dialogue-view/custom-dialogue-views.md). 

### How do I show the last line of text when options are shown? How do I skip the last line of text before a set of options?

Yarn Spinner automatically adds a `#lastline` tag to a line when the next step is a set of options. Create a [Custom Dialogue View](components/dialogue-view/custom-dialogue-views.md) that uses [`YarnProject.lineMetadata.GetMetadata()`](../api/csharp/yarn.unity.linemetadata.getmetadata.md) to check for `#lastline` and perform the behavior you want.

### How do I show the character name / portrait? How do I customize dialogue display?

To display _anything_ in Yarn Spinner, use a [Dialogue View](components/dialogue-view.md) component. [Line View](components/dialogue-view/line-view.md) for dialogue, [Options List View](components/dialogue-view/options-list-view.md) for choices.

Most projects will need custom views. We recommend a modular architecture where each UI element has its own LineView component. For example, a nameplate bubble has a [Dialogue Character Name View](../api/csharp/yarn.unity/yarn.unity.dialoguecharacternameview) that displays [`LocalizedLine.CharacterName`](../api/csharp/yarn.unity.localizedline.charactername.md), while the dialogue text window is another Line View that displays [`LocalizedLine.TextWithoutCharacterName`](../api/csharp/yarn.unity.localizedline.textwithoutcharactername.md). See [Creating Custom Dialogue Views](components/dialogue-view/custom-dialogue-views.md). 

For a working example, see the "Visual Novel" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "Visual Novel" and import it.) Specifically, see [VNManager.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/VisualNovel/Scripts/VNManager.cs) which inherits from DialogueViewBase, and changes the character name window background color (among other effects) based on the character name.

### How do I play a Yarn node when I click / tap on an object?

Write input code to detect clicking / tapping, then call `DialogueRunner.StartDialogue()`. 

The example tutorial [NPC Dialogue Game](sample-projects/example-project-3.md) can walk you through this step-by-step.

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

## System

### How do I generate a Yarn Project at runtime? How do I load/compile Yarn scripts at runtime?

The intended workflow is to generate and compile Yarn Projects at editor time, not runtime. See [Yarn Projects](importing-yarn-files/yarn-projects.md).

As of v2.x, Yarn Spinner Unity no longer supports runtime loading. Instead, Yarn Projects compile at editor time into bytecode. The source text and parser no longer ship with the game build. If you have specific runtime needs, you might be better off using Yarn Spinner Unity v1.x instead, or use a different Yarn implementation on a different platform -- see [Community Projects](../about/community-projects.md).

### How many Yarn files should I have? Can my entire game be in one project or script? Or one project per scene? Is my project or file too big?

There is no real technical limit on the number of Yarn scripts or the size of Yarn Projects. You decide how to organize your data, and every project has different needs. Some factors to consider:

- **Simplicity**. Putting everything into one big script file or one big project file is simpler sometimes.
- **Ease of writing**. Writers may prefer to think in terms of one file per scene, one file per chapter.
- **Localization**. 1 Yarn Project = 1 CSV spreadsheet per language. When translating, it is usually easier to work with fewer files, rather than fragmenting the translation across many files. As a workaround for games that need multiple Yarn Projects, you may prefer to create a single editor-only Yarn Project that's just for generating string files and translations. See [Localizations and Assets](./assets-and-localization/).
