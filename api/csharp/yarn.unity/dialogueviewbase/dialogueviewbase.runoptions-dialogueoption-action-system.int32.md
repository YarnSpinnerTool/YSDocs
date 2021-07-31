# RunOptions\(DialogueOption\[\], Action&lt;Int32&gt;\)

Called by the [`DialogueRunner`](../dialoguerunner/) to signal that a set of options should be displayed to the user.

```csharp
public abstract void RunOptions(DialogueOption[] dialogueOptions, Action<int> onOptionSelected)
```

## Remarks

When this method is called, the [`DialogueRunner`](../dialoguerunner/) will pause execution until the `onOptionSelected` method is called.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`DialogueOption[]`](../dialogueoption/) dialogueOptions | The set of options that should be displayed to the user. |
| `Action<Int32>` onOptionSelected | A method that should be called when the user has made a selection. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L108), line 108.

