# LinePresenter

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`DialoguePresenterBase`](yarn.unity.dialoguepresenterbase.md)

## Summary

A Dialogue Presenter that presents lines of dialogue, using Unity UI\
elements.

```csharp
public sealed class LinePresenter : DialoguePresenterBase
```

## Fields

| Name                                                                                   | Description                                                                                                                                     |
| -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| [autoAdvance](yarn.unity.linepresenter.autoadvance.md)                                 | Controls whether this Line View will automatically to the Dialogue Runner that the line is complete as soon as the line has finished appearing. |
| [autoAdvanceDelay](yarn.unity.linepresenter.autoadvancedelay.md)                       | The amount of time after the line finishes appearing before automatically ending the line, in seconds.                                          |
| [canvasGroup](yarn.unity.linepresenter.canvasgroup.md)                                 | The canvas group that contains the UI elements used by this Line View.                                                                          |
| [characterNameContainer](yarn.unity.linepresenter.characternamecontainer.md)           | The game object that holds the [characterNameText](yarn.unity.linepresenter.characternametext.md) text field.                                   |
| [characterNameText](yarn.unity.linepresenter.characternametext.md)                     | The `TMPro.TMP_Text` object that displays the character names found in dialogue lines.                                                          |
| [fadeDownDuration](yarn.unity.linepresenter.fadedownduration.md)                       | The time that the fade effect will take to fade lines out.                                                                                      |
| [fadeUpDuration](yarn.unity.linepresenter.fadeupduration.md)                           | The time that the fade effect will take to fade lines in.                                                                                       |
| [lineText](yarn.unity.linepresenter.linetext.md)                                       | The `TMPro.TMP_Text` object that displays the text of dialogue lines.                                                                           |
| [showCharacterNameInLineView](yarn.unity.linepresenter.showcharacternameinlineview.md) | Controls whether the [lineText](yarn.unity.linepresenter.linetext.md) object will show the character name present in the line or not.           |
| [temporalProcessors](yarn.unity.linepresenter.temporalprocessors.md)                   |                                                                                                                                                 |
| [typewriterEffectSpeed](yarn.unity.linepresenter.typewritereffectspeed.md)             | The number of characters per second that should appear during a typewriter effect.                                                              |
| [useFadeEffect](yarn.unity.linepresenter.usefadeeffect.md)                             | Controls whether the line view should fade in when lines appear, and fade out when lines disappear.                                             |
| [useTypewriterEffect](yarn.unity.linepresenter.usetypewritereffect.md)                 | Controls whether the text of [lineText](yarn.unity.linepresenter.linetext.md) should be gradually revealed over time.                           |

## Methods

| Name                                                                                                 | Description                                                                                                                              |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| [OnDialogueCompleteAsync()](yarn.unity.linepresenter.ondialoguecompleteasync.md)                     | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered. |
| [OnDialogueStartedAsync()](yarn.unity.linepresenter.ondialoguestartedasync.md)                       | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that dialogue has started.                                        |
| [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.linepresenter.runlineasync.md)        | Presents a line using the configured text view.                                                                                          |
| [RunOptionsAsync(DialogueOption\[\],CancellationToken)](yarn.unity.linepresenter.runoptionsasync.md) | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.            |
