# VoiceOverView

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from [`DialogueViewBase`](/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


Handles playback of voice over  <code>AudioClip</code> s referenced
on  <code>YarnScript</code> s.


```csharp
public class VoiceOverView : DialogueViewBase
```

## Fields

|Name|Description|
|:---|:---|
|[fadeOutTimeOnLineFinish](/api/csharp/yarn.unity.voiceoverview.fadeouttimeonlinefinish.md)|The fade out time when  <code>FinishCurrentLine</code>  is called.|
|[waitTimeAfterLineComplete](/api/csharp/yarn.unity.voiceoverview.waittimeafterlinecomplete.md)|The amount of time after playback has completed before this view reports that it's finished delivering the line.|
|[waitTimeBeforeLineStart](/api/csharp/yarn.unity.voiceoverview.waittimebeforelinestart.md)|The amount of time to wait before starting playback of the line.|

## Methods

|Name|Description|
|:---|:---|
|[DismissLine(Action)](/api/csharp/yarn.unity.voiceoverview.dismissline.md)||
|[InterruptLine(LocalizedLine,Action)](/api/csharp/yarn.unity.voiceoverview.interruptline.md)||
|[RunLine(LocalizedLine,Action)](/api/csharp/yarn.unity.voiceoverview.runline.md)|Start playback of the associated voice over  <code>AudioClip</code>  of the given  <a href="yarn.unity.localizedline.md">LocalizedLine</a> .|
|[UserRequestedViewAdvancement()](/api/csharp/yarn.unity.voiceoverview.userrequestedviewadvancement.md)||

