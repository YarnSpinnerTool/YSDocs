---
description: Common questions and solutions for using Yarn Spinner in Rust using Bevy.
---

# 💡 Frequently Asked Questions / "How Do I...?"

## Text

### How do I style text? How do I make some words bold, italic, colorful, etc.?

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

Note that _YS only processes the text data_. You must still code the actual markup effect yourself. See [Markup](../../write-yarn-scripts/editing-with-vs-code/markup.md).

## Variables

### How do I print the value of a variable in dialogue?

Wrap the variable (or any expression) in curly braces (`{`, `}`) to evaluate and output it. For more info, see [Variables](../../write-yarn-scripts/scripting-fundamentals/logic-and-variables/).

```
<<set $variableName to "a string value">>
The value of variableName is {$variableName}.
// This will appear as "The value of variableName is a string value."
```

### How do I read / write Yarn variables from Rust?

To read Yarn variables from Rust, use [`VariableStorage::get()`](https://docs.rs/yarnspinner/latest/yarnspinner/prelude/trait.VariableStorage.html#tymethod.get). To write Yarn variables from Rust, use [`VariableStorage::set()`](https://docs.rs/yarnspinner/latest/yarnspinner/prelude/trait.VariableStorage.html#tymethod.set)

{% hint style="info" %}
Don't forget the `$` when writing the variable's name!
{% endhint %}

```rust
let variable_storage = dialogue_runner.variable_storage_mut(); 
let test_variable: f32 = variable_storage.get("$testVariable")?.try_into()?;
variable_storage.set("$testVariable", (testVariable + 1).into())?;
```

### How do I 'sync' variables between Yarn and Rust?

You could hack this with static variables. But we recommend avoiding any "sync" pattern, because then you'll have to track and maintain the same data in two different places. Programmers usually prefer a ["single source of truth"](https://en.wikipedia.org/wiki/Single_source_of_truth). Data should live in only one place. Variables should either live in Yarn or live in Rust, and not in both.

### How do I load and save data / variables / dialogue state? (Like for a save game system)

To save the current node, save the value of [`DialogueRunner::current_node`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/struct.DialogueRunner.html#method.current_node) somewhere, e.g. to a `.ron` file. Then to restore it, call [`DialogueRunner.start_node()`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/struct.DialogueRunner.html#method.start_node) and pass in the saved node name.

To save variables, fetch them using [`DialogueRunner.variable_storage()`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/struct.DialogueRunner.html#method.variable_storage), then use [VariableStorage::variables](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/trait.VariableStorage.html#tymethod.variables) to read them all and store them again somewhere. Then to load variables, call [`VariableStorage::extend()`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/trait.VariableStorage.html#tymethod.extend).

For custom save systems, create your own [variable storage](components/variable-storage.md) by implementing [`VariableStorage`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/trait.VariableStorage.html) and its methods. Study [variable\_storage.rs](https://github.com/YarnSpinnerTool/YarnSpinner-Rust/blob/main/crates/runtime/src/variable_storage.rs) as an example.

It is not currently possible to save or restore the specific line that the dialogue is running.

## Control flow

### How do I jump to a specific node? How do I switch nodes while dialogue is running?

To jump to a node from Yarn, use `<<jump (nodeName)>>`. See [Nodes, Lines, and Options](../../write-yarn-scripts/scripting-fundamentals/lines-nodes-and-options.md).

To jump to a node with Rust, just call [`DialogueRunner.start_node("nodeName")`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/struct.DialogueRunner.html#method.start_node), even if there's already dialogue running.

### How do I jump to a specific line in a node?

Jumping to a specific line in a node is currently not supported. Instead, [jump to the start of a node](faq.md#how-do-i-jump-to-a-specific-node-how-do-i-switch-nodes-while-dialogue-is-running).

## Interaction / UI

### How do I show the last line of text when options are shown? How do I skip the last line of text before a set of options?

Yarn Spinner automatically adds a `#lastline` tag to a line when the next step is a set of options. Create a [Custom Dialogue View](components/dialogue-views.md) that uses [`StringInfo::metadata`](https://docs.rs/yarnspinner/latest/yarnspinner/prelude/struct.StringInfo.html#structfield.metadata) to check for "lastline" and perform the behavior you want.

### How do I show the character name / portrait? How do I customize dialogue display?

To display _anything_ in Yarn Spinner, use a [Dialogue View](components/dialogue-views.md) plugin.

### How do I make the Line View's Typewriter effect pause on punctuation?

Create a custom dialogue view with a custom effect based on [`typewriter.rs`](https://github.com/YarnSpinnerTool/YarnSpinner-Rust/blob/main/crates/example_dialogue_view/src/typewriter.rs) to detect the next text character and pause accordingly.

### How do I play a Yarn node when I click / tap on an object?

Write input code to detect clicking / tapping, then call [`DialogueRunner.start_node()`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/struct.DialogueRunner.html#method.start_node).

### How do I play a Yarn node when I approach an object and press a button? (RPG-like talking to NPCs)

This implementation will vary for every game, so we purposely do not attempt to design a one-size-fits-all generic NPC system. Here's some example pseudocode to make your own:

```
if (player presses SPACE)
    then find the nearest NPC
    get that NPC's dialogue node name
    call DialogueRunner.StartDialogue() with the NPC's dialogue node
    disable player movement
```

### How do I position a speech bubble above an NPC's head, like in A Short Hike?

The math / code is a little complicated. Calculate the NPC's on-screen position, then convert this screen position to UI canvas space, and reposition the dialogue bubble.

## System

### How many Yarn files should I have? Can my entire game be in one project or script? Or one project per scene? Is my project or file too big?

There is no real technical limit on the number of Yarn scripts or the size of Yarn Projects. You decide how to organize your data, and every project has different needs. Some factors to consider:

* **Simplicity**. Putting everything into one big script file or one big project file is simpler sometimes.
* **Ease of writing**. Writers may prefer to think in terms of one file per scene, one file per chapter.
* **Localization**. 1 Yarn Project = 1 CSV spreadsheet per language. When translating, it is usually easier to work with fewer files, rather than fragmenting the translation across many files. As a workaround for games that need multiple Yarn Projects, you may prefer to create a single editor-only Yarn Project that's just for generating string files and translations. See [Localizations](localisation.md).

## Other

### How do I credit Yarn Spinner in my game?

Please visit the [Crediting Yarn Spinner page](../../branding.md) for more information. Thanks for thinking of us!
