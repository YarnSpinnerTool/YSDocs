# GetLabelsForNode(string)

Method in [CompilationResult](yarn.compiler.compilationresult.md)

## Summary

Gets the mapping of instruction indices to named labels found in the\
node.

```csharp
public IReadOnlyDictionary<int, string> GetLabelsForNode(string node)
```

## Parameters

| Name          | Description           |
| ------------- | --------------------- |
| `string` node | The name of the node. |

## Returns

The instruction label mapping.
