# DialogueViewBase.DismissLine Method

Called by the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to signal that the
view should dismiss its current line from display, and clean
up.


```csharp
public abstract void DismissLine(Action onDismissalComplete)
```

## Parameters
|Parameter|Description|
|:---|:---|
|`Action` onDismissalComplete|The method that should be called when the view has finished dismissing the line.|


<div class="class-metadata">

Parent: [`DialogueViewBase`](/api/csharp/yarn.unity/dialogueviewbase.md), Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L93), line 93.
