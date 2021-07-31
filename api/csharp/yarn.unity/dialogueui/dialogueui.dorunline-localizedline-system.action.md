# DoRunLine\(LocalizedLine, System.Action\)

Shows a line of dialogue, gradually.

```csharp
protected IEnumerator DoRunLine(LocalizedLine dialogueLine, System.Action onDialogueLineFinished)
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`LocalizedLine`](../localizedline/) dialogueLine | The line to deliver. |
| [`Action`](https://docs.microsoft.com/dotnet/api/System.Action) onDialogueLineFinished | A callback to invoke when the text has finished appearing. |

## Return Type

`IEnumerator`

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L287), line 287.

