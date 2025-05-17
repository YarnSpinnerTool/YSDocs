# VoiceOverPresenter.RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [VoiceOverPresenter](/docs/api/csharp/yarn.unity.voiceoverpresenter.md)

## Summary


Begins playing the associated audio for the specified line.


```csharp
public override async YarnTask RunLineAsync(LocalizedLine dialogueLine, LineCancellationToken lineCancellationToken)
```

## Remarks

<p>
{% hint style="warning" %}
This method is not intended to be called from
your code. Instead, the [DialogueRunner](yarn.unity.dialoguerunner.md) class will call
it at the appropriate time.
{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
| line|The line to present.|
| token|A  [LineCancellationToken](yarn.unity.linecancellationtoken.md)  that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line.|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) dialogueLine||
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) lineCancellationToken||

## See Also

* [DialoguePresenterBase.RunLineAsync\(LocalizedLine,LineCancellationToken\)](/docs/api/csharp/yarn.unity.dialoguepresenterbase.runlineasync.md): Called by the  [DialogueRunner](yarn.unity.dialoguerunner.md)  to signal that a line should be displayed to the user.

