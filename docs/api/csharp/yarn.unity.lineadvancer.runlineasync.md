# LineAdvancer.RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [LineAdvancer](/docs/api/csharp/yarn.unity.lineadvancer.md)

## Summary


Called by a dialogue view to signal that a line is running.


```csharp
public override YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) line|The line to present.|
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) token|A  <a href="yarn.unity.linecancellationtoken.md">LineCancellationToken</a>  that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line.|

## Returns

A completed task.

