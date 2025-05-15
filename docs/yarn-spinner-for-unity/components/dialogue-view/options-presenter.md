---
description: '???'
---

# Options Presenter

An Option View is an object that the [Options List View](broken-reference) uses when presenting options. When the [Dialogue Runner](../dialogue-runner.md) delivers options to your game, Options List View will create an Option View for each option that could be selected.

When the Option View is pressed, the Options List View will notify the Dialogue Runner of the user's selection.

### Inspector

| Property            | Description                                                                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Text                | A TextMeshPro text object that will display the text of the line.                                                                                            |
| Show Character Name | If this is turned on, the Text component will show any character name present in the option. If this is turned off, the character name will not be included. |

An **Options List Presenter** is a [Dialogue Presenter](./) that presents a list of options in a list.

When this view receives options from the Dialogue Runner, it creates an instance of the [Option View](broken-reference) prefab you specify in the Option View Prefab property, and adds it as a child of the options list view.

{% hint style="info" %}
Options List View only displays options, and doesn't display lines. You can use an additional Dialogue View to handle these, like a [Line View](broken-reference) or a custom Dialogue View of your own.
{% endhint %}

### Inspector

| Property                 | Description                                                                                                                                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Canvas Group             | The Canvas Group that the Options List View will control. The Canvas Group will be made active when the Options List View is displaying options, and inactive when not displaying options.                         |
| Option View Prefab       | A prefab containing an Option View. The Options List View will create an instance of this prefab for each option that needs to be displayed.                                                                       |
| Last Line Text           | A TextMeshPro Text object that will display the text of the last line that appeared before options appeared. If this is not set, or no line has run before options are shown, then this property will not be used. |
| Fade Time                | The time, in seconds, that the Options List View will take to fade in. If this is zero, the Options List View will appear immediately.                                                                             |
| Show Unavailable Options | If this is turned on, then any options whose line condition has failed will still appear to the user, but they won't be selectable. If this is off, then these options will not appear at all.                     |
