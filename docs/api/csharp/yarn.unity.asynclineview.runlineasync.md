# AsyncLineView.RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [AsyncLineView](/docs/api/csharp/yarn.unity.asynclineview.md)

## Summary

Presents a line using the configured text view.

```csharp
public override async YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) line|The line to present.|
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) token|A  <a href="yarn.unity.linecancellationtoken.md">LineCancellationToken</a>  that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line.|

## Returns

A task that completes when the dialogue view has finished
showing the line to the user.

