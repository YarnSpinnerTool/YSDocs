# DialogueViewBase.MarkLineComplete Method

Signals that the user wants to go to the next line.


```csharp
public void MarkLineComplete()
```
## Remarks

This method is generally called by a "continue" button, and
causes the DialogueUI to signal the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to proceed to the next piece of
content.

If this method is called before the line has finished appearing
(that is, before the line's status changes to 
[`Delivered`](/api/csharp/yarn.unity/linestatus.delivered.md)), the line's status will
change to [`Interrupted`](/api/csharp/yarn.unity/linestatus.interrupted.md), and [`OnLineStatusChanged(LocalizedLine)`](/api/csharp/yarn.unity/dialogueviewbase.onlinestatuschanged-localizedline-.md) will be called to notify the view.




<div class="class-metadata">

Parent: [`DialogueViewBase`](/api/csharp/yarn.unity/dialogueviewbase.md), Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L162), line 162.
