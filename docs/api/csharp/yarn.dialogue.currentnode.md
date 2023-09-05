# Dialogue.CurrentNode

Property in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Gets the name of the node that this Dialogue is currently executing.


```csharp
public string CurrentNode
{
            get; }
```

## Remarks

If  <a href="yarn.dialogue.continue.md">Continue()</a>  has never been called, this value
will be  <code>null</code> .

