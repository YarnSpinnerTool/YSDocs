# BasicBlock.Name

Property in [BasicBlock](/api/csharp/yarn.compiler.basicblock.md)

## Summary


Gets a descriptive name for the block.


```csharp
public string Name
{
            get; }
```

## Remarks


If this block begins at a labelled instruction, the name will be  <code>[NodeName].[LabelName]</code> . Otherwise, it will be  <code>[NodeName].[FirstInstructionIndex]</code> .


