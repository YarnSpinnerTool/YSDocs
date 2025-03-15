# GetHeaders(string)

Method in [YarnProject](yarn.unity.yarnproject.md)

## Summary

Gets the headers for the requested node.

```csharp
public Dictionary<string, List<string>> GetHeaders(string nodeName)
```

## Remarks

The first time this is called, the values are extracted from [Program](yarn.unity.yarnproject.program.md) and cached inside `Yarn.Unity.YarnProject.nodeHeaders` . Future calls will then return the cached values.

## Parameters

| Name              | Description |
| ----------------- | ----------- |
| `string` nodeName |             |
