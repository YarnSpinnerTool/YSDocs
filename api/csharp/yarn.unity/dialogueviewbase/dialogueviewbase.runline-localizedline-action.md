# RunLine\(LocalizedLine, Action\)

Called by the [`DialogueRunner`](../dialoguerunner/) to signal that a line should be displayed to the user.

```csharp
public abstract void RunLine(LocalizedLine dialogueLine, Action onDialogueLineFinished)
```

## Remarks

If this method returns , it should not call the `onDialogueLineFinished` method.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`LocalizedLine`](../localizedline/) dialogueLine | The content of the line that should be presented to the user. |
| `Action` onDialogueLineFinished | The method that should be called after the line has been finished. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L68), line 68.

