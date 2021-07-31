# VoiceOverPlaybackUnity

Handles playback of voice over s referenced on s.

```csharp
public class VoiceOverPlaybackUnity : DialogueViewBase
```

## Methods

| Name | Description |
| :--- | :--- |
| [`DismissLine(Action)`](voiceoverplaybackunity.dismissline-action.md) |  |
| [`OnLineStatusChanged(LocalizedLine)`](voiceoverplaybackunity.onlinestatuschanged-localizedline.md) |  |
| [`RunLine(LocalizedLine, Action)`](voiceoverplaybackunity.runline-localizedline-action.md) | Start playback of the associated voice over  of the given [`LocalizedLine`](../localizedline/). |
| [`RunOptions(DialogueOption[], Action<Int32>)`](voiceoverplaybackunity.runoptions-dialogueoption-action-system.int32.md) | Yarn Spinner's implementation of voice over playback does nothing when presenting an option. |

## Fields

| Name | Description |
| :--- | :--- |
| [`fadeOutTimeOnLineFinish`](voiceoverplaybackunity.fadeouttimeonlinefinish.md) | The fade out time when  is called. |
| [`waitTimeAfterLineComplete`](voiceoverplaybackunity.waittimeafterlinecomplete.md) | The amount of time after playback has completed before this view reports that it's finished delivering the line. |
| [`waitTimeBeforeLineStart`](voiceoverplaybackunity.waittimebeforelinestart.md) | The amount of time to wait before starting playback of the line. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/VoiceOverPlaybackUnity.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/VoiceOverPlaybackUnity.cs#L10), line 10.

