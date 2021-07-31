# OnLineStatusChanged\(LocalizedLine\)

Called by the DialogueRunner to indicate that the line that this view is delivering has changed state.

```csharp
public abstract void OnLineStatusChanged(LocalizedLine dialogueLine)
```

## Remarks

Subclasses of [`DialogueViewBase`](./) should override this method to be notified when a line has become interrupted, and when the line has finished being delivered by all views.

The default implementation does nothing.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`LocalizedLine`](../localizedline/) dialogueLine | The [`LocalizedLine`](../localizedline/) that has changed state. |

## See Also

* [`LineStatus`](../linestatus/): 

  The presentation status of a [`LocalizedLine`](../localizedline/).

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L84), line 84.

