# CurrentNode

Property in [Dialogue](./)

## Summary

Gets the name of the node that this Dialogue is currently executing.

```csharp
public string CurrentNode
{
            get; }
```

## Remarks

If [Continue()](yarn.dialogue.continue.md) has never been called, this value will be `null` .
