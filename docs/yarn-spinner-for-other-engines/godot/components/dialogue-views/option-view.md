---
description: >-
  Learn about Options View, a component used to display an option in an Options
  List View.
---

# Option View

An Option View is an object that the [Options List View](options-list-view.md) uses when presenting options. When the [Dialogue Runner](../dialogue-runner.md) delivers options to your game, Options List View will create an Option View for each option that could be selected.

When the Option View is pressed, the Options List View will notify the Dialogue Runner of the user's selection.

### Inspector

| Property            | Description                                                                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Label               | A RichTextLabel node that will display the text of the line.                                                                                                 |
| Show Character Name | If this is turned on, the Text component will show any character name present in the option. If this is turned off, the character name will not be included. |
