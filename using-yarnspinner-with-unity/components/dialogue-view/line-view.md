---
description: >-
  Learn about Line View, a Dialogue View that displays a single line of dialogue
  on a Canvas.
---

# Line View

Line View is a [Dialogue View](./) that displays a single line of dialogue inside a Unity UI canvas. When the Dialogue Runner encounters a line in your Yarn Script, the Line View will display it, wait for the user to indicate they're done reading it, and then dismiss it.

{% hint style="info" %}
Line View only displays lines, and doesn't display options. You can use an additional Dialogue View to handle these, like an [Options List View](options-list-view.md) or a custom Dialogue View of your own.
{% endhint %}

### Showing the Character's Name

If a line contains a character's name at the start, Line View can be configured to show the name in a separate text view to the line text itself. If the Character Name Text property is connected to a TextMeshPro Text object, then the character's name will appear in this object.

If you don't attach a Text object to the Character Name Text property, you can choose to either show the character name as part of the line (that is, in the Line Text view), or don't show it all.

### Presenting Lines with Visual Effects

Line View can be configured to use visual effects when presenting lines.

* You can choose to have the Line View fade in when a line appears, and fade out when the line is dismissed.
* You can choose to have the text of the line appear, one letter at a time, with a "typewriter" effect.

### Continuing to the Next Line

The Dialogue Runner will automatically proceed to the next piece of content once all dialogue views have reported that they've finished with a line.

If the 'Auto Advance' option on a Line View is turned on, then the Line View will signal that it's done with a line as soon as all visual effects have finished.

If 'Auto Advance' is turned off, then the Line View will not signal that it's done when the effects have finished, and the line's delivery will stop. To make the Line View finish up, you can call the [UserRequestedViewAdvancement](../../../api/csharp/yarn.unity.lineview.userrequestedviewadvancement.md) method, which tells the Line View that the user wants to proceed. The built-in Dialogue System prefab comes set up with a 'Continue' button that calls this method. You can also call this method from code, or use the [Dialogue Advance Input](broken-reference) component to trigger it based on user input.

### Inspector

| Property                         | Description                                                                                                                                                                                                                                                                                                             |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Canvas Group                     | The Canvas Group that the Line View will control. The Canvas Group will be made active when the Line View is displaying a line, and inactive when not displaying a line.                                                                                                                                                |
| Auto Advance                     | If this is turned on, the Line View will finish presenting the line, and then wait. This is useful for games where the user has control over the timing of lines of dialogue. If this is turned off, the Line View will signal to the Dialogue Runner that it's done showing the line once all animations are complete. |
| Hold Time                        | If Auto Advance is turned on, the Line View will wait this many seconds after all animations are complete before signalling that it's done showing the line. This option is only available when Auto Advance is turned on.                                                                                              |
| Line Text                        | A TextMeshPro Text object that the text of the line will be displayed in.                                                                                                                                                                                                                                               |
| Use Fade Effect                  | If this is turned on, the Line View will fade the opacity of the Canvas Group from 0% to 100% opacity when lines appear, and fade back to 0% when lines are dismissed.                                                                                                                                                  |
| Fade In Time                     | The duration of the Fade effect when fading a new line in, in seconds. If this is zero, the line will appear immediately.                                                                                                                                                                                               |
| Fade Out Time                    | The duration of the Fade effect when fading a line out, in seconds. If this is zero, the line will disappear immediately.                                                                                                                                                                                               |
| Use Typewriter Effect            | If this is turned on, the text of the line will appear one character at a time. This will take place after the Fade effect, if enabled.                                                                                                                                                                                 |
| On Character Typed               | A Unity Event that's called every time the Typewriter effect displays new text.                                                                                                                                                                                                                                         |
| Typewriter Effect Speed          | The number of characters per second to display when performing a Typewrite effect. Larger values means that text will appear faster.                                                                                                                                                                                    |
| Character Name Text              | A TextMeshPro Text object that will display the name of the character currently speaking the line.                                                                                                                                                                                                                      |
| Show Character Name In Line View | If this is turned on, lines that contain a character's name will display the name in the Line Text section. If it is turned off, character names will not be shown at all. This option is only available when Character Name Text is empty.                                                                             |
| Continue Button                  | A game object that will be made active when the line has finished appearing. This is intended to be used for controlling the appearance of a button that the user can interact with to continue to the next line.                                                                                                       |
