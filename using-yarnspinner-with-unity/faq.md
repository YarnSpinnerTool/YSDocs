---
description: Common questions and common solutions for using Yarn Spinner in Unity.
---

# 💡 FAQ / How Do I... ?

## Q: How do I load / save variables? (Like for a save game system)

The Dialogue Runner has built-in support for saving variables to PlayerPref. https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.savestatetoplayerprefs

If you want to control your saving and loading yourself, we recommend creating your own variable storage, by subclassing VariableStorageBehaviour and implementing its methods. You can use the source code to InMemoryVariableStorage as a reference: https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/InMemoryVariableStorage.cs

## Q: How do I play a Yarn node when I approach an object and press a button? (RPG-like talking to NPCs)

See the "Space" sample project. (In Unity, go to `Window > Package Manager`, and select Yarn Spinner package. Expand the "Samples" dropdown and select "Space" and import it.)

Specifically, look at the C# sample [PlayerCharacter.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Samples~/Space/Scripts/PlayerCharacter.cs) for how to initiate a dialogue and search for nearby NPCs.

## Q: How do I style text? How do I make some words bold, italic, colorful, etc?

Yarn Spinner doesn't do text rendering, you have to use existing Unity systems like TextMeshPro. Fortunately, TMP supports HTML-like rich text tags. See the [TextMeshPro: Rich Text docs](https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/RichText.html) for more info.

```
Alice: This text is <b>bold!</b>
Bob: This text is <color=red>red!</color>

// NOTE: '#' is a special character in Yarn, used for line tags.
// To use a HTML color hex code, you must "escape" the "#" character with a "\"
Carol: Wow I'm <color=\#ff00ff>purple</color>!
```

TextMeshPro also lets you define Style Sheets, which make it easier to write with styles. See the [TextMeshPro: Style Sheets docs](https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/StyleSheets.html) for more info.

## Q: How do I make animated wavy text, like in Night In The Woods?

Again, Yarn Spinner doesn't handle text rendering. So you'll need to make you own / get your own wavy text system, like [Text Animator](https://assetstore.unity.com/packages/tools/gui/text-animator-for-unity-158707).
