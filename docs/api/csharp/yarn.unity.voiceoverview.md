# VoiceOverView

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](yarn.unity.asyncdialogueviewbase.md)

## Summary

A subclass of [AsyncDialogueViewBase](yarn.unity.asyncdialogueviewbase.md) that plays voice-over `UnityEngine.AudioClip` s for lines of dialogue.

```csharp
public class VoiceOverView : AsyncDialogueViewBase
```

## Fields

| Name                                                                                     | Description                                                                                                                                  |
| ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| [audioSource](yarn.unity.voiceoverview.audiosource.md)                                   | The `UnityEngine.AudioSource` that this voice over view will play its audio from.                                                            |
| [dialogueRunner](yarn.unity.voiceoverview.dialoguerunner.md)                             | The dialogue runner to notify of line completion.                                                                                            |
| [endLineWhenVoiceoverComplete](yarn.unity.voiceoverview.endlinewhenvoiceovercomplete.md) | If `true` , the voice over view will request that the dialogue runner proceed to the next line when audio for the line has finished playing. |
| [fadeOutTimeOnLineFinish](yarn.unity.voiceoverview.fadeouttimeonlinefinish.md)           | The fade out time when the line is interrupted during playback.                                                                              |
| [waitTimeAfterLineComplete](yarn.unity.voiceoverview.waittimeafterlinecomplete.md)       | The amount of time after playback has completed before this view reports that it's finished delivering the line.                             |
| [waitTimeBeforeLineStart](yarn.unity.voiceoverview.waittimebeforelinestart.md)           | The amount of time to wait before starting playback of the line.                                                                             |

## Methods

| Name                                                                                                 | Description                                                                                                                              |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| [OnDialogueCompleteAsync()](yarn.unity.voiceoverview.ondialoguecompleteasync.md)                     | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered. |
| [OnDialogueStartedAsync()](yarn.unity.voiceoverview.ondialoguestartedasync.md)                       | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that dialogue has started.                                        |
| [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.voiceoverview.runlineasync.md)        | Begins playing the associated audio for the specified line.                                                                              |
| [RunOptionsAsync(DialogueOption\[\],CancellationToken)](yarn.unity.voiceoverview.runoptionsasync.md) | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.            |

## See Also

* [DialogueViewBase](yarn.unity.dialogueviewbase.md): Implements the Yarn Spinner 2 callback-based API for dialogue views using Yarn Spinner 3.
