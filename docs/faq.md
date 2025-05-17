---
description: A FAQ for the various components overall Yarn Spinner project.
icon: puzzle
---

# FAQ

## FAQ for Yarn Spinner

<details>

<summary>Is Yarn Spinner a language? A tool for Unity? An editor?</summary>

**Yarn Spinner** isn't a single project, but is a collection of projects. Conceptually, we think of Yarn Spinner as having **Core Components**, some **Add-ons**, and some **Yarn Labs Experiments**.

{% hint style="danger" %}
If you're new to Yarn Spinner, you don't necessarily need to understand the components just yet. We **strongly recommend** starting at [start-here.md](write-yarn-scripts/start-here.md "mention").
{% endhint %}

#### Core Components

These are production-ready components, with stable, established, released versions:

* **Yarn**, the language you write your dialogue and narrative in: you write **Yarn Spinner Scripts** in **Yarn**.
* **Yarn Spinner for Visual Studio Code**, the _extension_ for the popular free text editor, Visual Studio Code, that gives it an understanding of the Yarn language, and helps you to write Yarn _scripts,_ with a graph visualisation tool, and other features.
* **Yarn Spinner for Unity**, the package you use to _import_ and _use_ your Yarn scripts in games you build in Unity.
* **Try Yarn Spinner**, an online tool that allows you to write Yarn scripts and Play them in a web browser. It's useful to write basic Yarn, and test things out. It's just a [website](https://try.yarnspinner.dev) you can visit!

⭐️ To learn to use the Core Components, jump into the [Beginner's Guide](/docs/beginners-guide.md).

#### Add-ons

These are projects that supply additional features to Yarn Spinner, and exist as add-ons to the free, open source projects that comprise the bulk of Yarn Spinner:

* **Dialogue Wheel for Yarn Spinner**, an add-on package for Yarn Spinner for Unity that provides Mass Effect-style dialogue wheel dialogue views.
* **Speech Bubbles for Yarn Spinner**, an add-on package for Yarn Spinner for Unity that provides customisable speech bubbles as dialogue views.

⭐️ To purchase the Add-ons, [visit the Yarn Spinner Itch.io Store](https://yarnspinner.itch.io), or the [Unity Asset Store](https://assetstore.unity.com/publishers/91946), or just [read the documentation](add-ons/about-add-ons.md).

#### Yarn Labs Experiments

These are experimental projects that are likely to eventually be released into Core, but are currently in early, or experimental stages:

* **Yarn Spinner for Unreal**, the package you use to _import_ and _use_ your _Yarn scripts_ in games you build in Unreal.
* **Yarn Spinner for Godot**, the package you use to _import_ and _use_ your _Yarn scripts_ in games you build in Godot.
* **Yarn Spinner for Rust**, the package that you use to _import_ and _use_ your _Yarn scripts_ in games you build using the Rust-based Bevy engine.

{% hint style="success" %}
**Yarn Spinner for Unreal** is moving from Yarn Labs to Core Components in 2025-2026.
{% endhint %}

### Start learning

If you're new to Yarn Spinner, we recommend that your next step is [start-here.md](write-yarn-scripts/start-here.md "mention")

</details>

<details>

<summary>Is Yarn Spinner free or paid? I heard it was Open Source?</summary>

Yarn Spinner is developed in the open, as open source software on GitHub. You can also install it from the source on GitHub, for free.

If you want to use Yarn Spinner for a commercial game, we recommend purchasing it from our [Itch.io Store](https://yarnspinner.itch.io/) or the [Unity Asset Store](https://assetstore.unity.com/packages/tools/behavior-ai/yarn-spinner-for-unity-267061). You can also contact us for a custom license, or to arrange consulting, support, or hire us to add features especially for you!

</details>

## FAQ for Yarn Spinner Scripts

<details>

<summary>What has changed for Yarn Spinner 3 vs. Yarn Spinner 2?</summary>

We've added a lot of new features, including [once.md](write-yarn-scripts/scripting-fundamentals/once.md "mention"), [detour.md](write-yarn-scripts/scripting-fundamentals/detour.md "mention"), [line-groups.md](write-yarn-scripts/scripting-fundamentals/line-groups.md "mention"), [node-groups.md](write-yarn-scripts/advanced-scripting/node-groups.md "mention"), and more. Yarn Spinner has a lot of features designed for storylets and saliency, and you can learn about those by reading through the [saliency.md](write-yarn-scripts/advanced-scripting/saliency.md "mention") guides here.

</details>

## FAQ for Yarn Spinner for Unity

<details>

<summary>Text</summary>

#### My text is not displaying at all?

You need to install the TextMeshPro Essential Resources. Open the Window menu -> TMP -> and choose **Import TMP Essential Resources.**

#### How do I style text? How do I make some words bold, italic, colorful, etc?

Yarn Spinner doesn't directly do text rendering, we use TextMeshPro to do the final render which has support for [rich-text](https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/RichText.html).\
However, writing TMP tags across a project is impractical so we have provided various styles and palettes via [Yarn Markup Attributes](write-yarn-scripts/advanced-scripting/markup.md).\
These provide a collection of common visual changes as well as offer a common interface\
There is a [sample](yarn-spinner-for-unity/samples/replacement-markup.md) showing off using the built in markup to style your text as well as how you can make your own Markup to do more advanced styling on your text.

#### How do I animate wavy text, like in Night In The Woods?

Yarn Spinner doesn't handle text rendering. You'll need a separate wavy text system, like [Text Animator](https://assetstore.unity.com/packages/tools/gui/text-animator-for-unity-158707).

#### How do I use Yarn Markup?

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

Note that _YS only processes the text data_. You must still code the actual markup effect yourself. See [Markup](write-yarn-scripts/advanced-scripting/markup.md).

</details>

<details>

<summary>Variables</summary>

#### How do I print the value of a variable in dialogue?

Wrap the variable (or any expression) in curly braces (`{`, `}`) to evaluate and output it. For more info, see [Variables](write-yarn-scripts/scripting-fundamentals/logic-and-variables.md).

```
<<set $variableName to "a string value">>
The value of variableName is {$variableName}.
// This will appear as "The value of variableName is a string value."
```

#### How do I read / write Yarn variables from a C# script?

You can register to be notified when a variable changes. To do this, in C#, call `AddChangeListener()` on a Line Provider and provide a delegate that should run when the variable changes:

```csharp
var stringListener = VarStorage.AddChangeListener("$stringVar", (string value) =>
{
    Debug.Log($"$stringVar changed to " + value);
});
```

When you no longer need to be notified of changes to a variable, you call `Dispose()` on the listener. If you don't do this, the variable storage will continue to call this delegate every time the variable changes, which you probably don't want to do.

```csharp
stringListener.Dispose();
```

​If you're implementing your own variable storage system, you must call the `NotifyVariableChanged()` method every time a variable changes value, in order to notify any change listeners:

```csharp
public override void SetValue(string variableName, float floatValue)
{
    // (code for updating the variable omitted)
    // Notify the change listeners that this variable changed
    NotifyVariableChanged(variableName, floatValue);
}
```

Alternatively, to read Yarn variables from C#, use `VariableStorageBehaviour.TryGetValue<T>()`.

To write Yarn variables from C#, use `VariableStorageBehaviour.SetValue()`.

{% hint style="info" %}
Don't forget the `$` when writing the variable's name!
{% endhint %}

```csharp
variableStorage = GameObject.FindObjectOfType<InMemoryVariableStorage>();
float testVariable;
variableStorage.TryGetValue("$testVariable", out testVariable);
variableStorage.SetValue("$testVariable", testVariable + 1);
```

You should also check out our [variable-storage](yarn-spinner-for-unity/components/variable-storage/ "mention") section, and the [custom-variable-storage.md](yarn-spinner-for-unity/components/variable-storage/custom-variable-storage.md "mention") guide.

#### How do I read / write C# variables from a Yarn script?

To read and write C# variables from Yarn, you must first code [Yarn Functions and Commands](yarn-spinner-for-unity/creating-commands-functions.md) in C#.

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

#### How do I 'sync' variables between Yarn and C#?

See the previous answers on working with variables. But we recommend avoiding any "sync" pattern, because then you'll have to track and maintain the same data in two different places. Programmers usually prefer a ["single source of truth"](https://en.wikipedia.org/wiki/Single_source_of_truth).

Data should live in only one place. Variables should **either** live in Yarn or live in C#, and **not in both**.

#### How do I load and save data / variables / dialogue state? (Like for a save game system)

To save the current node, save the value of [`DialogueRunner.CurrentNode`](/docs/api/csharp/yarn.dialogue.currentnode.md) somewhere. Then to restore it, call [`DialogueRunner.StartDialogue()`](/docs/api/csharp/yarn.unity.dialoguerunner.startdialogue.md) and pass in the saved node name.

To save variables, see [`DialogueRunner.SaveStateToPersistentStorage()`](/docs/api/csharp/yarn.unity.dialoguerunner.savestatetopersistentstorage.md). Then to load variables, call [`DialogueRunner.LoadStateFromPersistentStorage()`](/docs/api/csharp/yarn.unity.dialoguerunner.loadstatefrompersistentstorage.md). These methods use Unity's built-in JSON utility to serialize a dictionary of variables to the current platforms [persistent data path folder](https://docs.unity3d.com/6000.1/Documentation/ScriptReference/Application-persistentDataPath.html).

For custom save systems, create your own [variable storage](yarn-spinner-for-unity/components/variable-storage/variable-storage.md) by subclassing VariableStorageBehaviour and implementing its methods. Study [InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/InMemoryVariableStorage.cs) as an example. For more info, see [Guide: Yarn Variables and Variable Storage](yarn-spinner-for-unity/components/variable-storage/variable-storage.md).

</details>

<details>

<summary>Flow Control</summary>

#### How do I jump to a specific node? How do I switch nodes while dialogue is running?

To jump to a node from Yarn, use `<<jump (nodeName)>>`. See [Nodes, Lines, and Options](write-yarn-scripts/scripting-fundamentals/lines-nodes-and-options.md).

To jump to a node with C#, just call [`DialogueRunner.StartDialogue()`](/docs/api/csharp/yarn.unity.dialoguerunner.startdialogue.md).\
While you can jump to another node while dialogue is running we recommond **not** doing this and calling [`DialogueRunner.Stop()`](/docs/api/csharp/yarn.dialogue.stop.md) before starting another piece of dialogue.

#### How do I jump to a specific line in a node?

Jumping to a specific line in a node is currently not supported. Instead, [jump to the start of a node](faq.md#how-do-i-jump-to-a-specific-node-how-do-i-switch-nodes-while-dialogue-is-running).

</details>

<details>

<summary>Interaction/UI</summary>

#### How do I continue dialogue with key/button press instead of clicking the continue button?

This is demonstrated by the [Line Advancer component](yarn-spinner-for-unity/components/dialogue-view/dialogue-advance-input.md), which handles this exact scenario (among others).\
We recommend looking at how it handles the different ways of hurrying up or advancing lines as a starting point for your own games.

#### How do I show the last line of text when options are shown? How do I skip the last line of text before a set of options?

Yarn Spinner automatically adds a `#lastline` tag to a line when the next step is a set of options. Create a [Custom Dialogue Presenter](yarn-spinner-for-unity/components/dialogue-view/custom-dialogue-views.md) that uses [`YarnProject.lineMetadata.GetMetadata()`](/docs/api/csharp/yarn.unity.linemetadata.getmetadata.md) to check for "lastline" and perform the behavior you want.

#### How do I customize dialogue display?

To display _anything_ in Yarn Spinner, use a [Dialogue Presenter](yarn-spinner-for-unity/components/dialogue-view/custom-dialogue-views.md) component.\
There are two in-built presenters that demonstrate the basic functionality [Line Presenter](yarn-spinner-for-unity/components/dialogue-view/line-presenter.md) for lines of dialogue, [Options Presenter](yarn-spinner-for-unity/components/dialogue-view/options-presenter.md) for dialogue choices.

Most projects will need custom presenters.\
We recommend a modular architecture where each presenter handles it's own specific part of the display.\
An example of this is in the built in presenters the Line Presenter only handles showing lines, and the Options Presenter which only handles choices.

#### How do I make the Line Presenter's Typewriter pause?

You can pause the typewriter effect by using the built in pause markup:

```
Player: Sure would be nice if I could take a breather [pause /]  right now.
```

#### How do I play a Yarn node when I click / tap on an object?

Write input code to detect clicking / tapping, then call `DialogueRunner.StartDialogue()`.

#### How do I play a Yarn node when I approach an object and press a button? (RPG-like talking to NPCs)

This implementation will vary for every game, so we purposely do not attempt to design a one-size-fits-all generic NPC system. Here's some example pseudo-code to make your own:

```
if (player presses SPACE)
    then find the nearest NPC
    get that NPC's dialogue node name
    call DialogueRunner.StartDialogue() with the NPC's dialogue node
    disable player movement
```

The samples do have a shared script called the [Dialogue Interactible](https://github.com/YarnSpinnerTool/YarnSpinner-Unity-Samples/blob/main/Shared%20Assets/Scripts/DialogueInteractable.cs) which show off one way to achieve this behaviour.

#### How do I position a speech bubble above an NPC's head, like in A Short Hike?

The math / code is a little complicated. Calculate the NPC's on-screen position, then convert this screen position to UI canvas space, and reposition the dialogue bubble.\
We do have a [paid add-on](add-ons/speech-bubbles/) that handles all of this (and more) for you if you'd prefer to just have it all working.

#### How do I implement a resizing dialogue bubble / SMS messaging interface?

This is more about Unity UI rather than Yarn Spinner. For a working example, see the [Phone Chat](yarn-spinner-for-unity/samples/page-1.md) sample.

To make a resizing dialogue bubble that automatically fits text, you will need a complex UI setup. Study the UI game objects and components in the sample scene. For more context about how it works, see [this Unity UI Layout Groups explainer by Hallgrim Games](https://www.hallgrimgames.com/blog/2018/10/16/unity-layout-groups-explained).

#### How do I get text from a Text Input field into my Yarn story?

This mainly involves Unity UI, and assumes that your project already has a system where a player can input text like a TMPro Input Field component. If the player input needs to happen in the middle of dialogue execution then you can trigger it with a Yarn Command and wait for the player input if needed.

Once you have the player input value, you can store it in a C# variable and access it through a Yarn function, or store that value in a Yarn story variable. [FAQs for how to access variables in Yarn and YarnSpinner are here](faq.md#variables).

</details>

<details>

<summary>System</summary>

#### How do I generate a Yarn Project at runtime? How do I load/compile Yarn scripts at runtime?

The intended workflow is to generate and compile Yarn Projects at editor time, not runtime. See [Yarn Projects](yarn-spinner-for-unity/yarn-projects.md).

{% hint style="info" %}
Compiling a Yarn script at run-time is more complex than it first appears, because it often interacts with the very specific needs of your game, and we can't provide a one-size-fits-all approach to it. If you want to implement run-time loading in your own game, the place to start looking is the API documentation for the [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md) namespace. Please note that this is not something that we encourage people who are new to Yarn Spinner to do!
{% endhint %}

#### How many Yarn files should I have? Can my entire game be in one project or script? Or one project per scene? Is my project or file too big?

There is no real technical limit on the number of Yarn scripts or the size of Yarn Projects. You decide how to organize your data, and every project has different needs. Some factors to consider:

* **Simplicity**. Putting everything into one big script file or one big project file is simpler sometimes.
* **Ease of writing**. Writers may prefer to think in terms of one file per scene, one file per chapter.
* **Localization**. 1 Yarn Project = 1 CSV spreadsheet per language. When translating, it is usually easier to work with fewer files, rather than fragmenting the translation across many files. As a workaround for games that need multiple Yarn Projects, you may prefer to create a single editor-only Yarn Project that's just for generating string files and translations. See [Localizations and Assets](yarn-spinner-for-unity/assets-and-localization/).

</details>

<details>

<summary>Localization</summary>

#### How do I fetch any Yarn localized string in C#?

Some devs use YS to manage all in-game localized text, like UI strings. This use isn't intended, but it's possible. Manually create a Yarn.Line struct, set the line ID (see [Localization](yarn-spinner-for-unity/assets-and-localization/)), and then pass the struct into [`GetLocalizedLine()`](https://docs.yarnspinner.dev/api/csharp/yarn.unity/yarn.unity.lineproviderbehaviour/yarn.unity.lineproviderbehaviour.getlocalizedline).

```csharp
Yarn.Line targetLine = new Yarn.Line();
targetLine.ID = "line:lineid"; // replace 'lineid' with the actual line ID
LocalizedLine outputLine = LineProvider.GetLocalizedLine(targetLine);
Debug.Log(outputLine.Text.Text);

```

</details>

<details>

<summary>Other</summary>

#### How do I credit Yarn Spinner in my game?

Please visit the [Crediting Yarn Spinner page](branding.md) for more information.

#### Are there any examples of Yarn Spinner implementations in Unity?

Yes! We ship a whole collection of [samples](yarn-spinner-for-unity/samples/ "mention").

</details>
