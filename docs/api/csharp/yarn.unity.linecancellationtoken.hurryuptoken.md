# LineCancellationToken.HurryUpToken

Field in [LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)

## Summary


A  <code>System.Threading.CancellationToken</code>  that becomes cancelled when a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  wishes all dialogue views to speed up their
delivery of their line, if appropriate. For example, UI animations
should be played faster or skipped.


```csharp
public CancellationToken HurryUpToken;
```

## Remarks

This token is linked to  <a href="yarn.unity.linecancellationtoken.nextlinetoken.md">NextLineToken</a> : if the
next line token is cancelled, then this token will become cancelled
as well.

