---
description: Common questions and solutions for using Yarn Spinner in Unity.
---

# 💡 FAQ / How Do I... ?

## How do I style text? How do I make some words bold, italic, colorful, etc?

Yarn Spinner doesn't do text rendering, you have to use existing Unity systems like TextMeshPro. Fortunately, TMP supports HTML-like rich text tags. See the [TextMeshPro: Rich Text docs](https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/RichText.html) for more info.

```
Alice: This text is <b>bold!</b>
Bob: This text is <color=red>red!</color>

// NOTE: '#' is a special character in Yarn, used for line tags.
// To use a HTML color hex code, you must "escape" the "#" character with a "\"
Carol: Wow I'm <color=\#ff00ff>purple</color>!
```

However, this bespoke approach is impractical for longer scripts or bigger projects. We recommend using TextMeshPro's Style Sheets, which make it much easier to write consistently styled text. See the [TextMeshPro: Style Sheets docs](https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/StyleSheets.html) for more info.

## How do I animate wavy text, like in Night In The Woods?

Again, Yarn Spinner doesn't handle text rendering. So you'll need to make you own / get your own wavy text system, like [Text Animator](https://assetstore.unity.com/packages/tools/gui/text-animator-for-unity-158707).

## How do I read / write Yarn variables from a C# script?

To read Yarn variables from C#, use [`VariableStorageBehaviour.TryGetValue<T>()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.variablestoragebehaviour/yarn.unity.variablestoragebehaviour.trygetvalue). To write Yarn variables from C#, use [`VariableStorageBehaviour.SetValue()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.variablestoragebehaviour/yarn.unity.variablestoragebehaviour.setvalue-1). Don't forget the `$`.

```csharp
variableStorage = GameObject.FindObjectOfType<InMemoryVariableStorage>();
float testVariable;
variableStorage.TryGetValue("$testVariable", out testVariable);
variableStorage.SetValue("$testVariable", testVariable + 1);
```

## How do I read / write C# variables from a Yarn script?

To read and write C# variables from Yarn, use [Yarn Functions and Commands](creating-commands-functions.md). 

First, code the functions and commands in C#. Note that this implementation is `static`. See [Yarn Functions and Commands](creating-commands-functions.md) for more info.

```csharp
static int myNumber = 10;

[YarnFunction("getMyNumber")]
public static int GetMyNumber() { 
    return myNumber; 
}

[YarnCommand("setMyNumber")]
public static void SetMyNumber(int newNumber) { 
    myNumber = newNumber;
}
```

Then call the functions and commands in Yarn.

```
My number is { getMyNumber() }!
<<setMyNumber 999>>
But now it's { getMyNumber() }!
```

## How do I play a Yarn node when I approach an object and press a button? (RPG-like talking to NPCs)

This implementation will vary for every game, so Yarn Spinner purposely does not include an NPC system. Here's some example pseudocode to make your own:

```
if (player presses SPACE)
    then find the nearest NPC
    get that NPC's dialogue node name
    call DialogueRunner.StartDialogue() with the NPC's dialogue node
    disable player movement
```

For a working example, see the "Space" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "Space" and import it.) Specifically, see [PlayerCharacter.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/Space/Scripts/PlayerCharacter.cs) for how to search for nearby NPCs from a list.

## How do I position a speech bubble above an NPC's head, like in A Short Hike?

Using the built-in Unity UI canvas system, the math is a little complicated. You must calculate the NPC's on-screen position, then convert this screen position to UI canvas space and reposition the dialogue bubble.

For a working example, see the "3D" sample. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "3D" and import it.) Specfically, see [YarnCharacterView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/3D/Scripts/YarnCharacterView.cs) which has a method `WorldToAnchoredPosition()` that does a lot of this positioning math.

## How do I load and save data / variables / dialogue state? (Like for a save game system)

To save the current node, save the value of [`DialogueRunner.CurrentNodeName`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.currentnodename) somewhere, e.g. to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html). Then to restore it, call [`DialogueRunner.StartDialogue()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.startdialogue) and pass in the saved node name.

To save variables, see [`DialogueRunner.SaveStateToPlayerPrefs()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.savestatetoplayerprefs). Then to load variables, call [`DialogueRunner.LoadStateFromPlayerPrefs()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.loadstatefromplayerprefs). These methods use Unity's built-in JSON utility to serialize a dictionary of variables to Unity's [PlayerPrefs](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html).

For custom save systems, create your own [variable storage](components/variable-storage) by subclassing VariableStorageBehaviour and implementing its methods. Study [InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/InMemoryVariableStorage.cs) as an example. For more info, see [Guide: Yarn Variables and Variable Storage](../guides/yarn-variables-and-variable-storage).

**Currently, it is NOT possible to save/restore the current line nor the exact dialogue runner state.** The internal Yarn Virtual Machine is complicated, and gets even messier when intertwined with Unity game state. If you're an experienced coder who'd like to help, see [PR #242](https://github.com/YarnSpinnerTool/YarnSpinner/pull/242) for our last attempt at it.
