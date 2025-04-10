# GenerateUniqueVisitedVariableForNode(string)

Method in [Library](yarn.library.md)

## Summary

Generates a unique tracking variable name. This is intended to be used to generate names for visting. Ideally these will very reproduceable and sensible. For now it will be something terrible and easy.

```csharp
public static string GenerateUniqueVisitedVariableForNode(string nodeName)
```

## Parameters

| Name              | Description                                                          |
| ----------------- | -------------------------------------------------------------------- |
| `string` nodeName | The name of the node that needs to have a tracking variable created. |

## Returns

The new variable name.
