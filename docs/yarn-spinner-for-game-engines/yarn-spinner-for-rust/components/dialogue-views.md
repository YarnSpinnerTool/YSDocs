---
description: Learn about Dialogue Views, which present dialogue content to the user.
---

# Dialogue Views

Yarn Spinner itself handles only the hard logic behind the dialogue flow, but it doesn't actually draw _anything_ to the screen. This is the job of Dialogue Views. They are plugins that react to [`DialogueEvent`](https://docs.rs/yarnspinner/latest/yarnspinner/prelude/enum.DialogueEvent.html)s fired by the Dialogue Runner and display them to the player.

A Dialogue Runner can have multiple Dialogue Views. For example, you might have one Dialogue View that's designed to display lines of dialogue, and another that's in charge of displaying options to the player.

## Example Dialogue View

Because every game's needs are different, a Dialogue View is designed to be extremely customisable, and you can create your own custom dialogue views to suit the needs of your game.

However, because there are common patterns of how games work with dialogue, Yarn Spinner for Rust comes with a pre-built Dialogue View that handles common use cases: The [Example Dialogue View](https://docs.rs/bevy\_yarnspinner\_example\_dialogue\_view/latest/bevy\_yarnspinner\_example\_dialogue\_view/). You'll see it used all over our examples. To use it, you simply add its plugin after the Yarn Spinner plugin proper:

```rust
app.add_plugins((
    DefaultPlugins,
    YarnSpinnerPlugin::new(),
    ExampleYarnSpinnerDialogueViewPlugin::new(),
));
```

And that's it! It will display whatever comes its way to the user and handle some basic input. As an added bonus, it will send out a [`SpeakerChangeEvent`](https://docs.rs/bevy\_yarnspinner\_example\_dialogue\_view/latest/bevy\_yarnspinner\_example\_dialogue\_view/struct.SpeakerChangeEvent.html) whenever the active speaker has changed from its point of view, in case you want to e.g. rotate your camera there. If you do such an interaction, be sure to place your code in a Bevy system set that comes after the [`ExampleYarnSpinnerDialogueViewSystemSet`](https://docs.rs/bevy\_yarnspinner\_example\_dialogue\_view/latest/bevy\_yarnspinner\_example\_dialogue\_view/struct.ExampleYarnSpinnerDialogueViewSystemSet.html) to avoid race conditions.

## Custom Dialogue Views

To create your own Dialogue View, simply create a plugin that handles the different variants of [`DialogueEvent`](https://docs.rs/yarnspinner/latest/yarnspinner/prelude/enum.DialogueEvent.html) that come up during play. These are regular [Bevy events](https://github.com/bevyengine/bevy/blob/main/examples/ecs/event.rs) that you can handle using an [`EventReader`](https://docs.rs/bevy/latest/bevy/ecs/prelude/struct.EventReader.html). Make sure that you run your plugin in a Bevy system set after the [`YarnSpinnerSystemSet`](https://docs.rs/bevy\_yarnspinner/latest/bevy\_yarnspinner/prelude/struct.YarnSpinnerSystemSet.html) to catch all events that were sent in a given frame.

For inspiration, check out the source code of the [example Dialogue View](https://github.com/YarnSpinnerTool/YarnSpinner-Rust/tree/main/crates/example\_dialogue\_view/src).
