# VoiceOverView

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`DialogueViewBase`](yarn.unity.dialogueviewbase.md)

## Summary

A subclass of [DialogueViewBase](yarn.unity.dialogueviewbase.md) that plays voice-over `UnityEngine.AudioClip` s for lines of dialogue.

```csharp
public class VoiceOverView : DialogueViewBase
```

## Remarks

This class plays audio clip assets that are provided by an [AudioLineProvider](yarn.unity.audiolineprovider.md) . To use a [VoiceOverView](yarn.unity.voiceoverview.md) in your game, your [DialogueRunner](yarn.unity.dialoguerunner.md) must be configured to use an [AudioLineProvider](yarn.unity.audiolineprovider.md) , and your Yarn projects must be configured to use voice-over audio assets. For more information, see [Localization and Assets](../../using-yarnspinner-with-unity/assets-and-localization/).

## Fields

| Name                                                                               | Description                                                                                                                  |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| [audioSource](yarn.unity.voiceoverview.audiosource.md)                             | The `UnityEngine.AudioSource` that this voice over view will play its audio from.                                            |
| [fadeOutTimeOnLineFinish](yarn.unity.voiceoverview.fadeouttimeonlinefinish.md)     | The fade out time when [UserRequestedViewAdvancement()](yarn.unity.voiceoverview.userrequestedviewadvancement.md) is called. |
| [waitTimeAfterLineComplete](yarn.unity.voiceoverview.waittimeafterlinecomplete.md) | The amount of time after playback has completed before this view reports that it's finished delivering the line.             |
| [waitTimeBeforeLineStart](yarn.unity.voiceoverview.waittimebeforelinestart.md)     | The amount of time to wait before starting playback of the line.                                                             |

## Methods

| Name                                                                                       | Description                                                                                                                              |
| ------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| [DialogueComplete()](yarn.unity.voiceoverview.dialoguecomplete.md)                         | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered. |
| [DismissLine(Action)](yarn.unity.voiceoverview.dismissline.md)                             | Ends any existing playback, and reports that the line has finished dismissing.                                                           |
| [InterruptLine(LocalizedLine,Action)](yarn.unity.voiceoverview.interruptline.md)           | Interrupts the playback of the specified line, and quickly fades the playback to silent.                                                 |
| [RunLine(LocalizedLine,Action)](yarn.unity.voiceoverview.runline.md)                       | Begins playing the associated audio for the specified line.                                                                              |
| [UserRequestedViewAdvancement()](yarn.unity.voiceoverview.userrequestedviewadvancement.md) | Signals to this dialogue view that the user would like to skip playback.                                                                 |

## See Also

* [DialogueViewBase](yarn.unity.dialogueviewbase.md): A `UnityEngine.MonoBehaviour` that can present lines and options to the user, when it receives them from a [DialogueRunner](yarn.unity.dialoguerunner.md) .
