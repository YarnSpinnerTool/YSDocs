# LineProviderBehaviour.GetLocalizedLineAsync(Line,CancellationToken)

Method in [LineProviderBehaviour](/docs/api/csharp/yarn.unity.lineproviderbehaviour.md)

## Summary


Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the
specified  <a href="yarn.line.md">Line</a> .


```csharp
public abstract YarnLineTask GetLocalizedLineAsync(Line line, CancellationToken cancellationToken);
```

## Remarks


This method should not be called if  <a href="yarn.unity.lineproviderbehaviour.linesavailable.md">LinesAvailable</a>  returns  <code>false</code> .


## Parameters

|Name|Description|
|:---|:---|
|[Line](/docs/api/csharp/yarn.line.md) line|The  <a href="yarn.line.md">Line</a>  to produce the <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from.|
|`CancellationToken` cancellationToken||

## Returns

A localized line, ready to be presented to the
player.

