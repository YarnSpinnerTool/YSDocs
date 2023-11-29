# BasicBlock.PlayerVisibleContent

Property in [BasicBlock](/api/csharp/yarn.compiler.basicblock.md)

## Summary


Gets the collection of player-visible content that will be delivered
when this block is run.


```csharp
public IEnumerable<PlayerVisibleContentElement> PlayerVisibleContent
{
            get; }
```

## Remarks

<p>
Player-visible content means lines, options and commands. When this
block is run, the entire contents of this collection will be
displayed to the player, in the same order as they appear in this
collection.
</p> <p>
If this collection is empty, then the block contains no visible
content. This is the case for blocks that only contain logic, and do
not contain any lines, options or commands.
</p> <div class="example">
To tell the difference between the different kinds of content, use
the <code>is</code> operator to check the type of each item:
<pre>
foreach (var item in block.PlayerVisibleContent) { if (item is
LineElement line) { // Do something with line } }
</pre></div>

