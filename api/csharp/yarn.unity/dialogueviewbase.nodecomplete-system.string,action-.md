# DialogueViewBase.NodeComplete Method

Called by the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to signal that the
end of a node has been reached.


```csharp
public virtual void NodeComplete(string nextNode, Action onComplete)
```
## Remarks

This method may be called multiple times before [`DialogueComplete()`](/api/csharp/yarn.unity/dialogueviewbase.dialoguecomplete.md) is called. If this method returns
<see cref="!:Dialogue.HandlerExecutionType.ContinueExecution"></see>,
do not call the <code data-dev-comment-type="paramref" class="paramref">onComplete</code> method.

The default implementation does nothing.


## Parameters
|Parameter|Description|
|:---|:---|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) nextNode|The name of the next node that is being entered.|
|`Action` onComplete|A method that should be called to indicate that the DialogueRunner should continue executing.|


<div class="class-metadata">

Parent: [`DialogueViewBase`](/api/csharp/yarn.unity/dialogueviewbase.md), Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L130), line 130.
