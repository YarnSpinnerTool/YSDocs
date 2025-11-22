# NextLineToken

Field in [LineCancellationToken](yarn.unity.linecancellationtoken.md)

## Summary

A `System.Threading.CancellationToken` that becomes cancelled when a [DialogueRunner](yarn.unity.dialoguerunner.md) wishes all dialogue presenters to stop running\
the current line. For example, on-screen UI should be dismissed, and\
any ongoing audio playback should be stopped.

```csharp
public CancellationToken NextLineToken;
```
