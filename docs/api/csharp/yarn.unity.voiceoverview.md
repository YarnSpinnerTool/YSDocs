# VoiceOverView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)

## Summary


A subclass of  <a href="yarn.unity.asyncdialogueviewbase.md">AsyncDialogueViewBase</a>  that plays voice-over
<code>UnityEngine.AudioClip</code> s for lines of dialogue.


```csharp
public class VoiceOverView : AsyncDialogueViewBase
```

## Fields

|Name|Description|
|:---|:---|
|[audioSource](/docs/api/csharp/yarn.unity.voiceoverview.audiosource.md)|The  <code>UnityEngine.AudioSource</code>  that this voice over view will play its audio from.|
|[dialogueRunner](/docs/api/csharp/yarn.unity.voiceoverview.dialoguerunner.md)|The dialogue runner to notify of line completion.|
|[endLineWhenVoiceoverComplete](/docs/api/csharp/yarn.unity.voiceoverview.endlinewhenvoiceovercomplete.md)|If  <code>true</code> , the voice over view will request that the dialogue runner proceed to the next line when audio for the line has finished playing.|
|[fadeOutTimeOnLineFinish](/docs/api/csharp/yarn.unity.voiceoverview.fadeouttimeonlinefinish.md)|The fade out time when the line is interrupted during playback.|
|[waitTimeAfterLineComplete](/docs/api/csharp/yarn.unity.voiceoverview.waittimeafterlinecomplete.md)|The amount of time after playback has completed before this view reports that it's finished delivering the line.|
|[waitTimeBeforeLineStart](/docs/api/csharp/yarn.unity.voiceoverview.waittimebeforelinestart.md)|The amount of time to wait before starting playback of the line.|

## Methods

|Name|Description|
|:---|:---|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.voiceoverview.ondialoguecompleteasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.voiceoverview.ondialoguestartedasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that dialogue has started.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.voiceoverview.runlineasync.md)|Begins playing the associated audio for the specified line.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.voiceoverview.runoptionsasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.|

## See Also

* [DialogueViewBase](/docs/api/csharp/yarn.unity.dialogueviewbase.md): Implements the Yarn Spinner 2 callback-based API for dialogue views using Yarn Spinner 3.

