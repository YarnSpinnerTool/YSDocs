# VoiceOverView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`DialogueViewBase`](/docs/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that plays voice-over  <code>UnityEngine.AudioClip</code> s for lines of dialogue.


```csharp
public class VoiceOverView : DialogueViewBase
```

## Remarks


This class plays audio clip assets that are provided by an  <a href="yarn.unity.audiolineprovider.md">AudioLineProvider</a> . To use a  <a href="yarn.unity.voiceoverview.md">VoiceOverView</a>  in your
game, your  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  must be configured to use an
<a href="yarn.unity.audiolineprovider.md">AudioLineProvider</a> , and your Yarn projects must be
configured to use voice-over audio assets. For more information, see
[Localization and Assets](/docs/using-yarnspinner-with-unity/assets-and-localization/README.md).


## Fields

|Name|Description|
|:---|:---|
|[audioSource](/docs/api/csharp/yarn.unity.voiceoverview.audiosource.md)|The  <code>UnityEngine.AudioSource</code>  that this voice over view will play its audio from.|
|[fadeOutTimeOnLineFinish](/docs/api/csharp/yarn.unity.voiceoverview.fadeouttimeonlinefinish.md)|The fade out time when  <a href="yarn.unity.voiceoverview.userrequestedviewadvancement.md">UserRequestedViewAdvancement()</a>  is called.|
|[waitTimeAfterLineComplete](/docs/api/csharp/yarn.unity.voiceoverview.waittimeafterlinecomplete.md)|The amount of time after playback has completed before this view reports that it's finished delivering the line.|
|[waitTimeBeforeLineStart](/docs/api/csharp/yarn.unity.voiceoverview.waittimebeforelinestart.md)|The amount of time to wait before starting playback of the line.|

## Methods

|Name|Description|
|:---|:---|
|[DialogueComplete()](/docs/api/csharp/yarn.unity.voiceoverview.dialoguecomplete.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[DismissLine(Action)](/docs/api/csharp/yarn.unity.voiceoverview.dismissline.md)|Ends any existing playback, and reports that the line has finished dismissing.|
|[InterruptLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.voiceoverview.interruptline.md)|Interrupts the playback of the specified line, and quickly fades the playback to silent.|
|[RunLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.voiceoverview.runline.md)|Begins playing the associated audio for the specified line.|
|[UserRequestedViewAdvancement()](/docs/api/csharp/yarn.unity.voiceoverview.userrequestedviewadvancement.md)|Signals to this dialogue view that the user would like to skip playback.|

## See Also

* [DialogueViewBase](/docs/api/csharp/yarn.unity.dialogueviewbase.md): A  <code>UnityEngine.MonoBehaviour</code>  that can present lines and options to the user, when it receives them from a   <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .

