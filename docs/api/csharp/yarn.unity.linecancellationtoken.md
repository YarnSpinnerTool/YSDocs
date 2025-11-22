# LineCancellationToken

Struct in [Yarn.Unity](yarn.unity.md)

Inherits from `System.ValueType`

## Summary

A Line Cancellation Token stores information about whether a dialogue\
presenter should stop its delivery.

```csharp
public struct LineCancellationToken
```

## Remarks

Dialogue presenters receive Line Cancellation Tokens as a parameter to[RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.dialoguepresenterbase.runlineasync.md). Line Cancellation\
Tokens indicate whether the user has requested that the line's delivery\
should be hurried up, and whether the dialogue presenter should stop showing\
the current line.

## Fields

| Name                                                               | Description                                                                                                                                                                                                                                                                           |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [HurryUpToken](yarn.unity.linecancellationtoken.hurryuptoken.md)   | A `System.Threading.CancellationToken` that becomes cancelled when a [DialogueRunner](yarn.unity.dialoguerunner.md) wishes all dialogue presenters to speed up their delivery of their line, if appropriate. For example, UI animations should be played faster or skipped.           |
| [NextLineToken](yarn.unity.linecancellationtoken.nextlinetoken.md) | A `System.Threading.CancellationToken` that becomes cancelled when a [DialogueRunner](yarn.unity.dialoguerunner.md) wishes all dialogue presenters to stop running the current line. For example, on-screen UI should be dismissed, and any ongoing audio playback should be stopped. |

## Properties

| Name                                                                           | Description                                                                                    |
| ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| [IsHurryUpRequested](yarn.unity.linecancellationtoken.ishurryuprequested.md)   | Gets a value indicating whether the user has requested that the line be hurried up.            |
| [IsNextLineRequested](yarn.unity.linecancellationtoken.isnextlinerequested.md) | Gets a value indicating whether the dialogue runner has requested that the next line be shown. |
