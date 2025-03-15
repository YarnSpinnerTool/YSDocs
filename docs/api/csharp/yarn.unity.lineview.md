# LineView

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`DialogueViewBase`](yarn.unity.dialogueviewbase.md)

## Summary

A Dialogue View that presents lines of dialogue, using Unity UI elements.

```csharp
public class LineView : DialogueViewBase
```

## Fields

| Name                                                                              | Description                                                                                                                      |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| [autoAdvance](yarn.unity.lineview.autoadvance.md)                                 | Controls whether this Line View will wait for user input before indicating that it has finished presenting a line.               |
| [canvasGroup](yarn.unity.lineview.canvasgroup.md)                                 | The canvas group that contains the UI elements used by this Line View.                                                           |
| [characterNameContainer](yarn.unity.lineview.characternamecontainer.md)           | The gameobject that holds the [characterNameText](yarn.unity.lineview.characternametext.md) textfield.                           |
| [characterNameText](yarn.unity.lineview.characternametext.md)                     | The `TMPro.TextMeshProUGUI` object that displays the character names found in dialogue lines.                                    |
| [continueButton](yarn.unity.lineview.continuebutton.md)                           | The game object that represents an on-screen button that the user can click to continue to the next piece of dialogue.           |
| [fadeInTime](yarn.unity.lineview.fadeintime.md)                                   | The time that the fade effect will take to fade lines in.                                                                        |
| [fadeOutTime](yarn.unity.lineview.fadeouttime.md)                                 | The time that the fade effect will take to fade lines out.                                                                       |
| [holdTime](yarn.unity.lineview.holdtime.md)                                       | The amount of time to wait after any line                                                                                        |
| [lineText](yarn.unity.lineview.linetext.md)                                       | The `TMPro.TextMeshProUGUI` object that displays the text of dialogue lines.                                                     |
| [onCharacterTyped](yarn.unity.lineview.oncharactertyped.md)                       | A Unity Event that is called each time a character is revealed during a typewriter effect.                                       |
| [onPauseEnded](yarn.unity.lineview.onpauseended.md)                               | A Unity Event that is called when a pause inside of the typewriter effect finishes and the typewriter has started once again.    |
| [onPauseStarted](yarn.unity.lineview.onpausestarted.md)                           | A Unity Event that is called when a pause inside of the typewriter effect occurs.                                                |
| [palette](yarn.unity.lineview.palette.md)                                         |                                                                                                                                  |
| [showCharacterNameInLineView](yarn.unity.lineview.showcharacternameinlineview.md) | Controls whether the [lineText](yarn.unity.lineview.linetext.md) object will show the character name present in the line or not. |
| [typewriterEffectSpeed](yarn.unity.lineview.typewritereffectspeed.md)             | The number of characters per second that should appear during a typewriter effect.                                               |
| [useFadeEffect](yarn.unity.lineview.usefadeeffect.md)                             | Controls whether the line view should fade in when lines appear, and fade out when lines disappear.                              |
| [useTypewriterEffect](yarn.unity.lineview.usetypewritereffect.md)                 | Controls whether the text of [lineText](yarn.unity.lineview.linetext.md) should be gradually revealed over time.                 |

## Methods

| Name                                                                                                           | Description                                                                                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AddLineBreaks(Markup.MarkupParseResult)](yarn.unity.lineview.addlinebreaks.md)                                |                                                                                                                                                                                               |
| [DialogueComplete()](yarn.unity.lineview.dialoguecomplete.md)                                                  | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered.                                                      |
| [DismissLine(Action)](yarn.unity.lineview.dismissline.md)                                                      | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the view should dismiss its current line from display, and clean up.                                              |
| [GetPauseDurationsInsideLine(Markup.MarkupParseResult)](yarn.unity.lineview.getpausedurationsinsideline.md)    | Creates a stack of typewriter pauses to use to temporarily halt the typewriter effect.                                                                                                        |
| [InterruptLine(LocalizedLine,Action)](yarn.unity.lineview.interruptline.md)                                    | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible. |
| [OnContinueClicked()](yarn.unity.lineview.oncontinueclicked.md)                                                | Called when the [continueButton](yarn.unity.lineview.continuebutton.md) is clicked.                                                                                                           |
| [PaletteMarkedUpText(Markup.MarkupParseResult,MarkupPalette,bool)](yarn.unity.lineview.palettemarkeduptext.md) | Applies the `palette` to the line based on it's markup.                                                                                                                                       |
| [RunLine(LocalizedLine,Action)](yarn.unity.lineview.runline.md)                                                | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line should be displayed to the user.                                                                           |
| [UserRequestedViewAdvancement()](yarn.unity.lineview.userrequestedviewadvancement.md)                          | Called by [DialogueAdvanceInput](yarn.unity.dialogueadvanceinput.md) to signal that the user has requested that the dialogue advance.                                                         |
