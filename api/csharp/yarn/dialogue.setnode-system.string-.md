# Dialogue.SetNode Method

Prepares the [`Dialogue`](/api/csharp/yarn/dialogue.md) that the user intends to
start running a node.


```csharp
public void SetNode(string startNode = "Start")
```
## Remarks

After this method is called, you call [`Continue()`](/api/csharp/yarn/dialogue.continue.md) to
start executing it.

If [`PrepareForLinesHandler`](/api/csharp/yarn/dialogue.prepareforlineshandler.md) has been set, it may be
called when this method is invoked, as the Dialogue determines
which lines may be delivered during the <code data-dev-comment-type="paramref" class="paramref">startNode</code> node's execution.


## Parameters
|Parameter|Description|
|:---|:---|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) startNode|The name of the node that will be run. The node have been loaded by calling [`SetProgram(Program)`](/api/csharp/yarn/dialogue.setprogram-program-.md) or [`AddProgram(Program)`](/api/csharp/yarn/dialogue.addprogram-program-.md).|


## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L633), line 633.
