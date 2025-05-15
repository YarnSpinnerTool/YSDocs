# ILineProvider.GetLocalizedLineAsync(Line,CancellationToken)

Method in [ILineProvider](/docs/api/csharp/yarn.unity.ilineprovider.md)

## Summary


Prepares and returns a  [LocalizedLine](yarn.unity.localizedline.md)  from the specified
[Line](yarn.line.md) .


```csharp
public YarnTask<LocalizedLine> GetLocalizedLineAsync(Line line, CancellationToken cancellationToken);
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Line](/docs/api/csharp/yarn.line.md) line|The  [LocalizedLine](yarn.line.md">Line</a>  to produce the  <a href="yarn.unity.localizedline.md)  from.|
|`CancellationToken` cancellationToken|A cancellation token that indicates whether the process of fetching the localised version of  `line`  should be cancelled.|

## Returns

A localized line, ready to be presented to the
player.

