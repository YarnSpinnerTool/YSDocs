# SourceNodeName

Property in [Declaration](yarn.compiler.declaration.md)

## Summary

Gets the name of the node in which this Declaration was found.

```csharp
public string? SourceNodeName { get; internal set; }
```

## Remarks

If this [Declaration](yarn.compiler.declaration.md) was not found in a Yarn source file, this will be `null` .
