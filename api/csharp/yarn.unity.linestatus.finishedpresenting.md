# LineStatus.FinishedPresenting

Enumeration Member in [LineStatus](/api/csharp/yarn.unity.linestatus.md)

## Summary


The line has finished being delivered to the user.


```csharp
FinishedPresenting
```

## Remarks


When a line has finished being delivered, any animations in
showing text and any audio playback should now be complete. 

A line remains in the  <a href="yarn.unity.linestatus.finishedpresenting.md">FinishedPresenting</a>  state until a
Dialogue View calls  <a href="yarn.unity.dialogueviewbase.readyfornextline.md">ReadyForNextLine()</a> . At this point, the
line will transition to the  <a href="yarn.unity.linestatus.dismissed.md">Dismissed</a>  state, and  <a href="yarn.unity.dialogueviewbase.dismissline.md">DismissLine(Action)</a>  will be called on
all views to dismiss the line.


