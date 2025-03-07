---
description: Quickly get started with a simple scene.
---

# ⚡ Bevy Quick Start

We will now go through the steps to setup a new Bevy project running Yarn Spinner dialogues

## Setting up the crate

Run the following in your terminal to create a new crate with the required dependencies:

```bash
cargo new yarnspinner_playground
cd yarnspinner_playground
cargo add bevy bevy_yarnspinner bevy_yarnspinner_example_dialogue_view
```

The dependency `bevy_yarnspinner` is for the Yarn Spinner Bevy plugin proper, while `bevy_yarnspinner_example_dialogue_view` gives us a nice default [Dialogue View](components/dialogue-views.md), so we can actually see the text we've written and have options to click on.

## Adding the Yarn Files

We'll use a single Yarn file for this example. Inside the folder `assets/dialogue`, add a file named `example.yarn` with the following content:

```
# assets/dialogue/example.yarn
title: Start
---
Hello World!
Wow! My first ever Yarn script in Rust!

-> Gosh!
-> Incredible!
-> I'm amazed!

Anyway, time to get writing!
===
```

{% hint style="info" %}
You can learn about our recommended editor, Visual Studio Code with the official Yarn Spinner Extension at: [editing-with-vs-code.md](../write-yarn-scripts/writing-narratives/editing-with-vs-code.md "mention").
{% endhint %}

## The main code

Add the following code to your `src/main.rs`.

```rust
// src/main.rs
use bevy::{prelude::*, asset::ChangeWatcher, utils::Duration};
use bevy_yarnspinner::prelude::*;
use bevy_yarnspinner_example_dialogue_view::prelude::*;

fn main() {
    let mut app = App::new();
    app.add_plugins((
        DefaultPlugins,
        // Add the Yarn Spinner plugin. 
        // As soon as this plugin is built, a Yarn project will be compiled 
        // from all Yarn files found under assets/dialogue/*.yarn
        YarnSpinnerPlugin::new(),
        // Add the example dialogue view plugin
        ExampleYarnSpinnerDialogueViewPlugin::new(),
    ))
    // Setup a 2D camera so we can see the text
    .add_systems(Startup, setup_camera)
    // Spawn the dialog as soon as the Yarn project finished compiling
    .add_systems(
        Update,
        spawn_dialogue_runner.run_if(resource_added::<YarnProject>()),
    )
    .run();
}

fn setup_camera(mut commands: Commands) {
    commands.spawn(Camera2dBundle::default());
}

fn spawn_dialogue_runner(mut commands: Commands, project: Res<YarnProject>) {
    let mut dialogue_runner = project.create_dialogue_runner();
    // Start the dialog at the node with the title "Start"
    dialogue_runner.start_node("Start");
    commands.spawn(dialogue_runner);
}
```

Reiterating the comments in the code, let's take a look at some snippets.

```rust
YarnSpinnerPlugin::new(),
```

This self-explanatory line initializes the plugin. When using the standard constructor with no options, Yarn files will be searched for in the directory `<your game>/assets/dialogue/`, where all files ending in `.yarn` will be compiled as soon as the game starts.

The plugin makes sure all components of Yarn Spinner work except for any actual graphics. You need to instantiate a [Dialogue View](components/dialogue-views.md) for that:

```rust
ExampleYarnSpinnerDialogueViewPlugin::new(),
```

Here we initialize the dialogue view shipped by the `bevy_yarnspinner_example_dialogue_view` crate. It offers some sensible defaults which you can see in the screenshots used throughout this guide. You can of course skip this and use your own dialogue view instead.

```rust
spawn_dialogue_runner.run_if(resource_added::<YarnProject>()),
```

The method `.run_if(resource_added::<YarnProject>()` is our way of saying "run this system once as soon as our Yarn files are done compiling". Let's look at what will actually be run in that moment:

```rust
fn spawn_dialogue_runner(mut commands: Commands, project: Res<YarnProject>) {
    let mut dialogue_runner = project.create_dialogue_runner();
    // Start the dialog at the node with the title "Start"
    dialogue_runner.start_node("Start");
    commands.spawn(dialogue_runner);
}
```

The main way of interacting with Yarn files during runtime and managing the flow of a dialog is through a [`DialogueRunner`](components/dialogue-runner.md). To do this, we use the [`YarnProject`](yarn-projects.md) resource we referenced in the `run_if` section above. It represents our compiled Yarn files, which we use to create a new dialog runner.\
We then point it to the [node](../write-yarn-scripts/syntax-basics/lines-nodes-and-options.md) named "Start" of our Yarn file. We use `start_node` for this, which will "move" the dialog runner to the provided node and start executing the dialog in the next frame, using the registered Dialogue View to actually present it on the screen.\
Finally, we spawn the dialog runner on an own entity into the Bevy world.

In the end, your file structure should look like this:

![file\_system.png](../.gitbook/assets/file_system.png)

Run your game with `cargo run` and you should see the following:

![hello\_world.png](../.gitbook/assets/hello_world.png)
