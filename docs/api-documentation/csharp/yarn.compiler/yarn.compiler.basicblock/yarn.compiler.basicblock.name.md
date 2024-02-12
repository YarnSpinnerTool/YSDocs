# Name

Property in [BasicBlock](./)

## Summary

Gets a descriptive name for the block.

```csharp
public string Name
{
            get; }
```

## Remarks

If this block begins at a labelled instruction, the name will be `[NodeName].[LabelName]` . Otherwise, it will be `[NodeName].[FirstInstructionIndex]` .
