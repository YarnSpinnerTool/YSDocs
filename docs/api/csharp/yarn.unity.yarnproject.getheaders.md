# YarnProject.GetHeaders(string)

Method in [YarnProject](/docs/api/csharp/yarn.unity.yarnproject.md)

## Summary


Gets the headers for the requested node.


```csharp
public Dictionary<string, List<string>> GetHeaders(string nodeName)
```

## Remarks


The first time this is called, the values are extracted from
<a href="yarn.unity.yarnproject.program.md">Program</a>  and cached inside  <code>Yarn.Unity.YarnProject.nodeHeaders</code> .
Future calls will then return the cached values.


## Parameters

|Name|Description|
|:---|:---|
|`string` nodeName||

