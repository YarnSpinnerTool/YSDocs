# YarnProject.GetLineIDsForNodes(IEnumerable<string>)

Method in [YarnProject](/api/csharp/yarn.unity.yarnproject.md)

## Summary


Returns a list of all line and option IDs within the requested nodes


```csharp
public IEnumerable<string> GetLineIDsForNodes(IEnumerable<string> nodes)
```

## Remarks


This is intended to be used either to precache multiple nodes worth of lines or for debugging


## Parameters

|Name|Description|
|:---|:---|
|`System.Collections.Generic.IEnumerable<string>` nodes|the names of all nodes whos line IDs you covet|

## Returns

The ids of all lines and options in the requested  <code>nodes</code>

