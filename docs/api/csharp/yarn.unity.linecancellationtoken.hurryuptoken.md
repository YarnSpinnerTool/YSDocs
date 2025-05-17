# LineCancellationToken.HurryUpToken

Field in [LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)

## Summary


A  `System.Threading.CancellationToken`  that becomes cancelled when a  [DialogueRunner](yarn.unity.dialoguerunner.md)  wishes all dialogue views to speed up their
delivery of their line, if appropriate. For example, UI animations
should be played faster or skipped.


```csharp
public CancellationToken HurryUpToken;
```

## Remarks

This token is linked to  [NextLineToken](yarn.unity.linecancellationtoken.nextlinetoken.md) : if the
next line token is cancelled, then this token will become cancelled
as well.

