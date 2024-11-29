# VoiceOverView.RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [VoiceOverView](/docs/api/csharp/yarn.unity.voiceoverview.md)

## Summary


Begins playing the associated audio for the specified line.


```csharp
public override async YarnTask RunLineAsync(LocalizedLine dialogueLine, LineCancellationToken lineCancellationToken)
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
| line|The line to present.|
| token|A  <a href="yarn.unity.linecancellationtoken.md">LineCancellationToken</a>  that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line.|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) dialogueLine||
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) lineCancellationToken||

## See Also

* [AsyncDialogueViewBase.RunLineAsync\(LocalizedLine,LineCancellationToken\)](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.runlineasync.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.

