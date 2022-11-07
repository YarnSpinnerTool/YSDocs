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

Again, Yarn Spinner doesn't handle text rendering. You'll need a separate wavy text system, like [Text Animator](https://assetstore.unity.com/packages/tools/gui/text-animator-for-unity-158707).

### How do I use Yarn Markup?

Markup lets you mark a range of text (words, phrases) in a generic way, for whatever use. You could use it to style text, add sentence markers, make clickable words, etc. Note that Yarn Spinner only processes the text data. You must still code the actual effect yourself. See [Markup](../getting-started/writing-in-yarn/markup.md).

```
// Yarn script example of custom "wavy text" markup.
Oh, [wave]hello[/wave] there!

// After compiling, text will look like: "Oh, hello there!"
// And then the resulting markup data will look like:
// - name: "wave"
// - position: 4
// - length: 5
```

(TODO: there should be an easier way for working with markup in dialogue views? At least for simple open/close tag text replacement)

## Variables

### How do I print the value of a variable in dialogue?

Wrap the variable (or any expression) in curly braces (`{`, `}`) to evaluate and output it. For more info, see [Variables](../getting-started/writing-in-yarn/logic-and-variables.md).

```
<<set $variableName to "a string value">>
The value of variableName is {$variableName}.
```

### How do I read / write Yarn variables from a C# script?

To read Yarn variables from C#, use [`VariableStorageBehaviour.TryGetValue<T>()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.variablestoragebehaviour/yarn.unity.variablestoragebehaviour.trygetvalue). To write Yarn variables from C#, use [`VariableStorageBehaviour.SetValue()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.variablestoragebehaviour/yarn.unity.variablestoragebehaviour.setvalue-1). Don't forget the `$`.

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

### How do I 'sync' variables between Yarn and C#?

See the previous answers on working with variables. But we recommend avoiding any "sync" pattern, because then you'll have to track and maintain the same data in two different places. Programmers usually prefer a ["single source of truth"](https://en.wikipedia.org/wiki/Single_source_of_truth). Data should live in only one place. Variables should either live in Yarn or live in C#, and not in both.

### How do I load and save data / variables / dialogue state? (Like for a save game system)

To save the current node, save the value of [`DialogueRunner.CurrentNodeName`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.currentnodename) somewhere, e.g. to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html). Then to restore it, call [`DialogueRunner.StartDialogue()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.startdialogue) and pass in the saved node name.

To save variables, see [`DialogueRunner.SaveStateToPlayerPrefs()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.savestatetoplayerprefs). Then to load variables, call [`DialogueRunner.LoadStateFromPlayerPrefs()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.loadstatefromplayerprefs). These methods use Unity's built-in JSON utility to serialize a dictionary of variables to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html).

For custom save systems, create your own [variable storage](components/variable-storage.md) by subclassing VariableStorageBehaviour and implementing its methods. Study [InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/InMemoryVariableStorage.cs) as an example. For more info, see [Guide: Yarn Variables and Variable Storage](../guides/yarn-variables-and-variable-storage.md).

**Currently it is NOT possible to save/restore the current line nor the exact dialogue runner state.** It's complicated. If you're an experienced coder who'd like to help, see [PR #242](https://github.com/YarnSpinnerTool/YarnSpinner/pull/242) for our last attempt at it.

## Control flow

### How do I jump to a specific node? How do I switch nodes while dialogue is running?

To jump to a node from Yarn, use `<<jump (nodeName)>>`. See [Nodes, Lines, and Options](../getting-started/writing-in-yarn/lines-nodes-and-options.md).

To jump to a node with C#, just call [`DialogueRunner.StartDialogue()`](../api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.startdialogue), even if there's already dialogue running.

### How do I jump to a specific line in a node?

Currently it is not possible to do this. It's complicated. If you're an experienced coder who'd like to help, see [PR #242](https://github.com/YarnSpinnerTool/YarnSpinner/pull/242) for our last attempt at it.

## Interaction / UI

### How do I continue dialogue with key/button press instead of clicking the continue button?

In most cases, use the [Dialogue Advance Input](components/dialogue-view/dialogue-advance-input.md). 

For more control, call [`UserRequestedViewAdvancement()`](../api/csharp/yarn.unity/yarn.unity.lineview/yarn.unity.lineview.userrequestedviewadvancement) on a Dialogue View, or [`OnContinuedClicked()`](../api/csharp/yarn.unity/yarn.unity.lineview/yarn.unity.lineview.oncontinueclicked) on a Line View. See [Creating Custom Dialogue Views](components/dialogue-view/custom-dialogue-views.md). 

### How do I show the last line of text when options are shown? How do I skip the last line of text before a set of options?

(TODO: this should really be built into Dialogue Runner or Dialogue Views by now?)

As of v2.2, Yarn Spinner automatically adds a `#lastline` tag to a line when the next step is a set of options...

### How do I show the character name / portrait? How do I customize dialogue display?

To display _anything_ in Yarn Spinner, use a [Dialogue View](components/dialogue-view.md) component. [Line View](components/dialogue-view/line-view.md) for dialogue, [Options List View](components/dialogue-view/options-list-view.md) for choices.

Most projects will need custom views. We recommend a modular architecture where each UI element has its own LineView component. For example, a nameplate bubble has a [Dialogue Character Name View](../api/csharp/yarn.unity/yarn.unity.dialoguecharacternameview) that displays [`LocalizedLine.CharacterName`](../api/csharp/yarn.unity/yarn.unity.localizedline/yarn.unity.localizedline.charactername), while the dialogue text window is another Line View that displays [`LocalizedLine.TextWithoutCharacterName`](../api/csharp/yarn.unity/yarn.unity.localizedline/yarn.unity.localizedline.textwithoutcharactername). See [Creating Custom Dialogue Views](components/dialogue-view/custom-dialogue-views.md). 

For a working example, see the "Visual Novel" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "Visual Novel" and import it.) Specifically, see [VNManager.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/VisualNovel/Scripts/VNManager.cs) which inherits from DialogueViewBase, and changes the character name window background color (among other effects) based on the character name.

### How do I play a Yarn node when I approach an object and press a button? (RPG-like talking to NPCs)

This implementation will vary for every game, so Yarn Spinner purposely does not include an NPC system. Here's some example pseudocode to make your own:

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

For a working example, see the "3D" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "3D" and import it.) Specfically, see [YarnCharacterView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/3D/Scripts/YarnCharacterView.cs) which has a method `WorldToAnchoredPosition()` that does a lot of this positioning math.

## System

### How do I generate a Yarn Project at runtime? How do I load/compile Yarn scripts at runtime?

The intended workflow is to generate and compile Yarn Projects at editor time, not runtime. See [Yarn Projects](importing-yarn-files/yarn-projects.md).

As of v2.x, Yarn Spinner Unity no longer supports runtime loading. Instead, Yarn Projects compile at editor time into bytecode. The source text and parser no longer ship with the game build. If you have specific runtime needs, you might be better off using Yarn Spinner Unity v1.x instead, or use a different Yarn implementation on a different platform -- see [Community Projects](../about/community-projects.md).

### How many Yarn files should I have? Can my entire game be in one project or script? Or one project per scene? Is my project or file too big?

There is no real technical limit on the number of Yarn scripts or the size of Yarn Projects. You decide how to organize your data, and every project has different needs. Some factors to consider:

- **Simplicity**. Putting everything into one big script file or one big project file is certainly simpler.
- **Ease of writing**. Writers may prefer to think in terms of scenes or chapters.
- **Localization**. 1 Yarn Project = 1 language CSV. Translators often prefer to work with one file or few files, instead of many files. (As a workaround, you may want to keep one mega editor-only Yarn Project containing every single Yarn file, and only use this project file for managing localization.)
- **Platform**. While bytecode and text are somewhat cheap compared to other game data, a huge 100,000 word project should probably be split into multiple script files or project files. But you never know. Different consoles or devices may have different limits. In the end, you just have to profile it.
