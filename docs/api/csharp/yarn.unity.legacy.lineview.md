# LineView

Class in [Yarn.Unity.Legacy](yarn.unity.legacy.md)

Inherits from [`DialogueViewBase`](yarn.unity.legacy.dialogueviewbase.md)

{% hint style="warning" %}
This class is obsolete and may be removed from a future version of Yarn Spinner.
{% endhint %}

## Summary

A Dialogue View that presents lines of dialogue, using Unity UI\
elements.

```csharp
public class LineView : DialogueViewBase
```

## Fields

| Name                                                                                     | Description                                                                                                                             |
| ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| [autoAdvance](yarn.unity.legacy.lineview.autoadvance.md)                                 | Controls whether this Line View will wait for user input before indicating that it has finished presenting a line.                      |
| [canvasGroup](yarn.unity.legacy.lineview.canvasgroup.md)                                 | The canvas group that contains the UI elements used by this Line View.                                                                  |
| [characterNameContainer](yarn.unity.legacy.lineview.characternamecontainer.md)           | The gameobject that holds the [characterNameText](yarn.unity.legacy.lineview.characternametext.md) textfield.                           |
| [characterNameText](yarn.unity.legacy.lineview.characternametext.md)                     | The `TMPro.TextMeshProUGUI` object that displays the character names found in dialogue lines.                                           |
| [continueButton](yarn.unity.legacy.lineview.continuebutton.md)                           | The game object that represents an on-screen button that the user can click to continue to the next piece of dialogue.                  |
| [fadeInTime](yarn.unity.legacy.lineview.fadeintime.md)                                   | The time that the fade effect will take to fade lines in.                                                                               |
| [fadeOutTime](yarn.unity.legacy.lineview.fadeouttime.md)                                 | The time that the fade effect will take to fade lines out.                                                                              |
| [holdTime](yarn.unity.legacy.lineview.holdtime.md)                                       | The amount of time to wait after any line                                                                                               |
| [lineText](yarn.unity.legacy.lineview.linetext.md)                                       | The `TMPro.TextMeshProUGUI` object that displays the text of dialogue lines.                                                            |
| [onCharacterTyped](yarn.unity.legacy.lineview.oncharactertyped.md)                       | A Unity Event that is called each time a character is revealed during a typewriter effect.                                              |
| [onPauseEnded](yarn.unity.legacy.lineview.onpauseended.md)                               | A Unity Event that is called when a pause inside of the typewriter effect finishes and the typewriter has started once again.           |
| [onPauseStarted](yarn.unity.legacy.lineview.onpausestarted.md)                           | A Unity Event that is called when a pause inside of the typewriter effect occurs.                                                       |
| [palette](yarn.unity.legacy.lineview.palette.md)                                         |                                                                                                                                         |
| [showCharacterNameInLineView](yarn.unity.legacy.lineview.showcharacternameinlineview.md) | Controls whether the [lineText](yarn.unity.legacy.lineview.linetext.md) object will show the character name present in the line or not. |
| [typewriterEffectSpeed](yarn.unity.legacy.lineview.typewritereffectspeed.md)             | The number of characters per second that should appear during a typewriter effect.                                                      |
| [useFadeEffect](yarn.unity.legacy.lineview.usefadeeffect.md)                             | Controls whether the line view should fade in when lines appear, and fade out when lines disappear.                                     |
| [useTypewriterEffect](yarn.unity.legacy.lineview.usetypewritereffect.md)                 | Controls whether the text of [lineText](yarn.unity.legacy.lineview.linetext.md) should be gradually revealed over time.                 |

## Methods

| Name                                                                                                                  | Description                                                                                                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AddLineBreaks(Markup.MarkupParseResult)](yarn.unity.legacy.lineview.addlinebreaks.md)                                | Inserts TextMeshPro line break markup in a line where Yarn line break attributes appear.                                                                                                      |
| [DialogueComplete()](yarn.unity.legacy.lineview.dialoguecomplete.md)                                                  | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered.                                                      |
| [DismissLine(Action)](yarn.unity.legacy.lineview.dismissline.md)                                                      | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the view should dismiss its current line from display, and clean up.                                              |
| [InterruptLine(LocalizedLine,Action)](yarn.unity.legacy.lineview.interruptline.md)                                    | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible. |
| [OnContinueClicked()](yarn.unity.legacy.lineview.oncontinueclicked.md)                                                | Called when the [continueButton](yarn.unity.legacy.lineview.continuebutton.md) is clicked.                                                                                                    |
| [PaletteMarkedUpText(Markup.MarkupParseResult,MarkupPalette,bool)](yarn.unity.legacy.lineview.palettemarkeduptext.md) | Applies the `palette` to the line based on it's markup.                                                                                                                                       |
| [RunLine(LocalizedLine,Action)](yarn.unity.legacy.lineview.runline.md)                                                | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line should be displayed to the user.                                                                           |
| [UserRequestedViewAdvancement()](yarn.unity.legacy.lineview.userrequestedviewadvancement.md)                          | Called by [DialogueAdvanceInput](yarn.unity.legacy.dialogueadvanceinput.md) to signal that the user has requested that the dialogue advance.                                                  |
