# RunOptionsAsync(DialogueOption\[],CancellationToken)

Method in [DialogueCharacterNameView](yarn.unity.dialoguecharacternameview.md)

## Summary

Takes no action; this dialogue view does not handle options.

```csharp
public override YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken)
```

## Parameters

| Name                                                                          | Description                                                                                                                                                                              |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| line                                                                          | The line to present.                                                                                                                                                                     |
| token                                                                         | A [LineCancellationToken](yarn.unity.linecancellationtoken.md) that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line. |
| [Yarn.Unity.DialogueOption\[\]](yarn.unity.dialogueoption.md) dialogueOptions |                                                                                                                                                                                          |
| `CancellationToken` cancellationToken                                         |                                                                                                                                                                                          |

## Returns

A task that completes when the dialogue view has finished showing the line to the user.
