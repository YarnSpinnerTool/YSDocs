# Descendants

Property in [BasicBlock](yarn.compiler.basicblock.md)

## Summary

Gets all descendants (that is, destinations, and destinations of those destinations, and so on), recursively.

```csharp
public IEnumerable<BasicBlock> Descendants
{
            get; }
```

## Remarks

Cycles are detected and avoided.
