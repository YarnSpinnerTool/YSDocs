# UnityLocalisedLineProvider.GetLocalizedLineAsync(Line,CancellationToken)

Method in [UnityLocalisedLineProvider](/docs/api/csharp/yarn.unity.unitylocalization.unitylocalisedlineprovider.md)

## Summary


Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the specified
<a href="yarn.line.md">Line</a> .


```csharp
public override async YarnTask<LocalizedLine> GetLocalizedLineAsync(Line line, CancellationToken cancellationToken)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Line](/docs/api/csharp/yarn.line.md) line|The  <a href="yarn.line.md">Line</a>  to produce the  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from.|
|`CancellationToken` cancellationToken|A cancellation token that indicates whether the process of fetching the localised version of  <code>line</code>  should be cancelled.|

## Returns

A localized line, ready to be presented to the
player.

