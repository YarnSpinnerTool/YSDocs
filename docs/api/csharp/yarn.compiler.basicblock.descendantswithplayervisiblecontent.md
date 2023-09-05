# BasicBlock.DescendantsWithPlayerVisibleContent

Property in [BasicBlock](/api/csharp/yarn.compiler.basicblock.md)

## Summary


Gets all descendants (that is, destinations, and destinations of
those destinations, and so on) that have any player-visible content,
recursively.


```csharp
public IEnumerable<BasicBlock> DescendantsWithPlayerVisibleContent
{
            get; }
```

## Remarks


Cycles are detected and avoided.


