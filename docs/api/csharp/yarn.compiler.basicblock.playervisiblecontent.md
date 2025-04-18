# PlayerVisibleContent

Property in [BasicBlock](yarn.compiler.basicblock.md)

## Summary

Gets the collection of player-visible content that will be delivered when this block is run.

```csharp
public IEnumerable<PlayerVisibleContentElement> PlayerVisibleContent
{
            get; }
```

## Remarks

Player-visible content means lines, options and commands. When this block is run, the entire contents of this collection will be displayed to the player, in the same order as they appear in this collection.

If this collection is empty, then the block contains no visible content. This is the case for blocks that only contain logic, and do not contain any lines, options or commands.

To tell the difference between the different kinds of content, use the `is` operator to check the type of each item:

```
foreach (var item in block.PlayerVisibleContent) { if (item is
LineElement line) { // Do something with line } }
```
