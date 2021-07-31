# NodeComplete\(String, Action\)

Called by the [`DialogueRunner`](../dialoguerunner/) to signal that the end of a node has been reached.

```csharp
public virtual void NodeComplete(string nextNode, Action onComplete)
```

## Remarks

This method may be called multiple times before [`DialogueComplete()`](dialogueviewbase.dialoguecomplete.md) is called. If this method returns

, do not call the `onComplete` method.

The default implementation does nothing.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) nextNode | The name of the next node that is being entered. |
| `Action` onComplete | A method that should be called to indicate that the DialogueRunner should continue executing. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L130), line 130.

