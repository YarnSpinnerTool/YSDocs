# Commands

[Commands](../../../write-yarn-scripts/commands.md) work very similar to Yarn [functions](creating-functions.md), but use a different syntax and are able to modify the game world. As a consequence of their similarity, registering custom commands is very similar to registering [custom functions](creating-functions.md).

## Command Registration

Just as with Yarn functions, registration happens when creating a `DialogueRunner`. Let's again modify the example from the [Quick Start](../quick-start.md):

```rust
fn spawn_dialogue_runner(mut commands: Commands, project: Res<YarnProject>) {
    let mut dialogue_runner = project.create_dialogue_runner();
    // Add our custom command to the dialogue runner
    dialogue_runner
        .commands_mut()
        .add_command("print_addition", print_addition);
    dialogue_runner.start_node("Start");
    commands.spawn(dialogue_runner);
}

fn print_addition(In((a, b)): In<(f32, f32)>) {
    print!("{a} + {b} = {c}", c = a + b)
}
```

We call the command like this:

```
title: Start
---
Let's print the addition of 1 and 3 in the console:
<<print_addition 1 3>>
===
```

You will have seen one crucial difference to Yarn functions immediately. The parameters are not passed in directly to the Rust function, but are wrapped in an `In` struct. This is because Rust functions that are registered as commands are always valid Bevy systems. The `In` parameter just tells the function which values come from the Yarn file, but we can additionally query the Bevy world as we want:

```rust
fn spawn_dialogue_runner(mut commands: Commands, project: Res<YarnProject>) {
    let mut dialogue_runner = project.create_dialogue_runner();
    // Add our custom command to the dialogue runner
    dialogue_runner
        .commands_mut()
        .add_command("insert_resource", insert_resource);
    dialogue_runner.start_node("Start");
    commands.spawn(dialogue_runner);
}

#[derive(Resource)]
struct Person {
    name: String,
    age: f32,
}

fn insert_resource(In((name, age)): In<(String, f32)>, mut commands: Commands) {
    commands.insert_resource(Person { name, age });
}
```

which we call like this:

```
title: Start
---
Let's insert a resource into the Bevy world:
<<insert_resource "Bob" 42>>
===
```

{% hint style="info" %}
The Rust functions serving as commands always require an `In` parameter. If your Yarn command doesn't accept any parameters, specify the first parameter in Rust like this: `fn my_command(_: In<()>, ...)`
{% endhint %}

## Return Types and Long Running Commands

In contrast to [functions](creating-functions.md), commands cannot have any Yarn facing return types. The Rust functions however can use a return value to indicate that Yarn Spinner should wait a while before continuing the dialogue. This is useful for times when you want to change something in the world before the dialogue goes on, e.g. move the camera to another speaker. To do this, simply return a type implementing [`TaskFinishedIndicator`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/trait.TaskFinishedIndicator.html), for example `Arc<AtomicBool>`. This way, you can keep a copy of the `Arc` and change its content to `true` whenever your transition is over.

For a practical example, check out how we [implement a fade out](https://github.com/YarnSpinnerTool/YarnSpinner-Rust/blob/main/demo/src/yarnspinner_integration.rs#L114) at the end of the [demo](https://janhohenheim.itch.io/yarnspinner-rust-demo).
