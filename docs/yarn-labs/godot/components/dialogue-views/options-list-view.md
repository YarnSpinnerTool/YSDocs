---
description: >-
  Learn about Options List View, a Dialogue View that displays a list dialogue
  options.
---

# Options List View

Options List View is a [Dialogue View](./) that presents a list of options in a list.

When this view receives options from the Dialogue Runner, it creates an instance of the [Option View](option-view.md) prefab you specify in the Option View Prefab property, and adds it as a child of the options list view.

{% hint style="info" %}
Options List View only displays options, and doesn't display lines. You can use an additional Dialogue View to handle these, like a [Line View](line-view.md) or a custom Dialogue View of your own.
{% endhint %}

### Inspector

| Property                 | Description                                                                                                                                                                                                   |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Canvas Group             | The Canvas Group that the Options List View will control. The Canvas Group will be made active when the Options List View is displaying options, and inactive when not displaying options.                    |
| Option View Prefab       | A packed scene containing an Option View. The Options List View will create an instance of this packed scene for each option that needs to be displayed.                                                      |
| Last Line Text           | A RichTextLabel node that will display the text of the last line that appeared before options appeared. If this is not set, or no line has run before options are shown, then this property will not be used. |
| Fade Time                | The time, in seconds, that the Options List View will take to fade in. If this is zero, the Options List View will appear immediately.                                                                        |
| Show Unavailable Options | If this is turned on, then any options whose line condition has failed will still appear to the user, but they won't be selectable. If this is off, then these options will not appear at all.                |
| Pallete                  | An optional MarkupPallete resource. Used to represent a collection of marker names and colours.                                                                                                               |
