---
description: Learn about Dialogue Views, which present dialogue content to the user.
---

# Dialogue Views

A Dialogue View is a kind of node that receives content from a Dialogue Runner, and presents it to the player. Dialogue Views are how the player sees your game's lines of dialogue, and how they select choices in the dialogue.

A Dialogue Runner can have multiple Dialogue Views. For example, you might have one Dialogue View that's designed to display lines of dialogue, and another that's in charge of displaying options to the player.

Because every game's needs are different, a Dialogue View is designed to be extremely customizable, and you can [create your own custom dialogue views](custom-dialogue-views.md) to suit the needs of your game.

However, because there are common patterns of how games work with dialogue, Yarn Spinner for Godot comes with some pre-built Dialogue Views that handle common use cases:

* [Line View](line-view.md) is a Dialogue View that displays a single line of dialogue in a RichTextLabel on a CanvasLayer, and shows a button that the user can click to proceed.
* [Option List View](options-list-view.md) is a Dialogue View that displays a collection of options in a list.
