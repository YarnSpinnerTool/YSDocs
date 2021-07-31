# Delivered

The line has been fully presented to the user. A view class presenting the line as text would be showing the entire line and a view class playing voice over clips would be silent now.

```csharp
Delivered = 2
```

## Remarks

A line that was previously [`Interrupted`](linestatus.interrupted.md) will become [`Delivered`](linestatus.delivered.md) once the [`DialogueViewBase`](../dialogueviewbase/) has completed the interruption process.

## See Also

* [`LineStatus`](./): 

  The presentation status of a [`LocalizedLine`](../localizedline/).

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L1478), line 1478.

