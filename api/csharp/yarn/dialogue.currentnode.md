# Dialogue.CurrentNode Property

Gets the name of the node that this Dialogue is currently
executing.


```csharp
public string CurrentNode { get; }
```
## Remarks
If [`Continue()`](/api/csharp/yarn/dialogue.continue.md) has never been called, this
value will be `null`.



## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L738), line 738.
