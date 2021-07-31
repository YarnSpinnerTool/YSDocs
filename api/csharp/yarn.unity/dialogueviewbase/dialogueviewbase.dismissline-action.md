# DismissLine\(Action\)

Called by the [`DialogueRunner`](../dialoguerunner/) to signal that the view should dismiss its current line from display, and clean up.

```csharp
public abstract void DismissLine(Action onDismissalComplete)
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| `Action` onDismissalComplete | The method that should be called when the view has finished dismissing the line. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L93), line 93.

