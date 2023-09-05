# LineProviderBehaviour.GetLocalizedLine(Yarn.Line)

Method in [LineProviderBehaviour](/api/csharp/yarn.unity.lineproviderbehaviour.md)

## Summary


Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the
specified  <code>Yarn.Line</code> .


```csharp
public abstract LocalizedLine GetLocalizedLine(Yarn.Line line);
```

## Remarks


This method should not be called if  <a href="yarn.unity.lineproviderbehaviour.linesavailable.md">LinesAvailable</a>  returns  <code>false</code> .


## Parameters

|Name|Description|
|:---|:---|
|`Yarn.Line` line|The  <code>Yarn.Line</code>  to produce the <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from.|

## Returns

A localized line, ready to be presented to the
player.

