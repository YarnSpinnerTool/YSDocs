# DialogueViewBase.ReadyForNextLine()

Method in [DialogueViewBase](/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


Signals that the user wants to go to the next line.


```csharp
public void ReadyForNextLine()
```

## Remarks


This method is generally called by a "continue" button, and
causes the DialogueUI to signal the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to proceed to the next piece of
content.

If this method is called before the line has finished appearing
(that is, before the line's status changes to  <a href="yarn.unity.linestatus.finishedpresenting.md">FinishedPresenting</a> ), the line's status will change
to  <a href="yarn.unity.linestatus.interrupted.md">Interrupted</a> , and  <a href="yarn.unity.dialogueviewbase.onlinestatuschanged.md">OnLineStatusChanged(LocalizedLine)</a>  will be called to notify the view.


