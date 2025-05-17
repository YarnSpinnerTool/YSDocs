# LineCancellationToken.NextLineToken

Field in [LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)

## Summary


A  `System.Threading.CancellationToken`  that becomes cancelled when a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  wishes all dialogue views to stop running
the current line. For example, on-screen UI should be dismissed, and
any ongoing audio playback should be stopped.


```csharp
public CancellationToken NextLineToken;
```

