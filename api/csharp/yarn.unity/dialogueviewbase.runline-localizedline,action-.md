# DialogueViewBase.RunLine Method

Called by the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to signal that a
line should be displayed to the user.


```csharp
public abstract void RunLine(LocalizedLine dialogueLine, Action onDialogueLineFinished)
```
## Remarks

If this method returns <see cref="!:Dialogue.HandlerExecutionType.ContinueExecution"></see>, it
should not call the <code data-dev-comment-type="paramref" class="paramref">onDialogueLineFinished</code>
method.


## Parameters
|Parameter|Description|
|:---|:---|
|[`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md) dialogueLine|The content of the line that should be presented to the user.|
|`Action` onDialogueLineFinished|The method that should be called after the line has been finished.|


<div class="class-metadata">

Parent: [`DialogueViewBase`](/api/csharp/yarn.unity/dialogueviewbase.md), Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L68), line 68.
