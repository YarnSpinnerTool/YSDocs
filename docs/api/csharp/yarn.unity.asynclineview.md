# AsyncLineView

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](yarn.unity.asyncdialogueviewbase.md)

## Summary

A Dialogue View that presents lines of dialogue, using Unity UI elements.

```csharp
public class AsyncLineView : AsyncDialogueViewBase
```

## Fields

| Name                                                                                   | Description                                                                                                                                     |
| -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| [autoAdvance](yarn.unity.asynclineview.autoadvance.md)                                 | Controls whether this Line View will automatically to the Dialogue Runner that the line is complete as soon as the line has finished appearing. |
| [autoAdvanceDelay](yarn.unity.asynclineview.autoadvancedelay.md)                       | The amount of time after the line finishes appearing before automatically ending the line, in seconds.                                          |
| [canvasGroup](yarn.unity.asynclineview.canvasgroup.md)                                 | The canvas group that contains the UI elements used by this Line View.                                                                          |
| [characterNameContainer](yarn.unity.asynclineview.characternamecontainer.md)           | The game object that holds the [characterNameText](yarn.unity.asynclineview.characternametext.md) text field.                                   |
| [characterNameText](yarn.unity.asynclineview.characternametext.md)                     | The `TMPro.TMP_Text` object that displays the character names found in dialogue lines.                                                          |
| [continueButton](yarn.unity.asynclineview.continuebutton.md)                           | The `UnityEngine.UI.Button` that represents an on-screen button that the user can click to continue to the next piece of dialogue.              |
| [fadeDownDuration](yarn.unity.asynclineview.fadedownduration.md)                       | The time that the fade effect will take to fade lines out.                                                                                      |
| [fadeUpDuration](yarn.unity.asynclineview.fadeupduration.md)                           | The time that the fade effect will take to fade lines in.                                                                                       |
| [lineText](yarn.unity.asynclineview.linetext.md)                                       | The `TMPro.TMP_Text` object that displays the text of dialogue lines.                                                                           |
| [onCharacterTyped](yarn.unity.asynclineview.oncharactertyped.md)                       | A Unity Event that is called each time a character is revealed during a typewriter effect.                                                      |
| [showCharacterNameInLineView](yarn.unity.asynclineview.showcharacternameinlineview.md) | Controls whether the [lineText](yarn.unity.asynclineview.linetext.md) object will show the character name present in the line or not.           |
| [temporalProcessors](yarn.unity.asynclineview.temporalprocessors.md)                   | A list of [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md) objects that will be used to handle markers in the line.                 |
| [typewriterEffectSpeed](yarn.unity.asynclineview.typewritereffectspeed.md)             | The number of characters per second that should appear during a typewriter effect.                                                              |
| [useFadeEffect](yarn.unity.asynclineview.usefadeeffect.md)                             | Controls whether the line view should fade in when lines appear, and fade out when lines disappear.                                             |
| [useTypewriterEffect](yarn.unity.asynclineview.usetypewritereffect.md)                 | Controls whether the text of [lineText](yarn.unity.asynclineview.linetext.md) should be gradually revealed over time.                           |

## Methods

| Name                                                                                                 | Description                                                                                                                              |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| [OnDialogueCompleteAsync()](yarn.unity.asynclineview.ondialoguecompleteasync.md)                     | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered. |
| [OnDialogueStartedAsync()](yarn.unity.asynclineview.ondialoguestartedasync.md)                       | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that dialogue has started.                                        |
| [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.asynclineview.runlineasync.md)        | Presents a line using the configured text view.                                                                                          |
| [RunOptionsAsync(DialogueOption\[\],CancellationToken)](yarn.unity.asynclineview.runoptionsasync.md) | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.            |
