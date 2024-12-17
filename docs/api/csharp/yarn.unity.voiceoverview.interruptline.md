# VoiceOverView.InterruptLine(LocalizedLine,Action)

Method in [VoiceOverView](/docs/api/csharp/yarn.unity.voiceoverview.md)

## Summary


Interrupts the playback of the specified line, and quickly fades the
playback to silent.


```csharp
public override void InterruptLine(LocalizedLine dialogueLine, Action onDialogueLineFinished)
```

## Remarks

<p>
{% hint style="warning" %}
This method is not intended to be called from
your code. Instead, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> class will call
it at the appropriate time.
{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) dialogueLine|The current line that is being presented.|
|`Action` onDialogueLineFinished|The method that should be called after the line has finished being presented.|

## See Also

* [DialogueViewBase.InterruptLine\(LocalizedLine,Action\)](/docs/api/csharp/yarn.unity.dialogueviewbase.interruptline.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.

