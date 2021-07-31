# MarkLineComplete\(\)

Signals that the user wants to go to the next line.

```csharp
public void MarkLineComplete()
```

## Remarks

This method is generally called by a "continue" button, and causes the DialogueUI to signal the [`DialogueRunner`](../dialoguerunner/) to proceed to the next piece of content.

If this method is called before the line has finished appearing \(that is, before the line's status changes to [`Delivered`](../linestatus/linestatus.delivered.md)\), the line's status will change to [`Interrupted`](../linestatus/linestatus.interrupted.md), and [`OnLineStatusChanged(LocalizedLine)`](dialogueviewbase.onlinestatuschanged-localizedline.md) will be called to notify the view.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L162), line 162.

