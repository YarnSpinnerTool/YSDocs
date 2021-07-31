# CurrentNode

Gets the name of the node that this Dialogue is currently executing.

```csharp
public string CurrentNode { get; }
```

## Remarks

If [`Continue()`](dialogue.continue.md) has never been called, this value will be `null`.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L738), line 738.

