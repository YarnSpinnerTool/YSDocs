# RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [DialogueCharacterNameView](yarn.unity.dialoguecharacternameview.md)

## Summary

Invokes the [onNameUpdate](yarn.unity.dialoguecharacternameview.onnameupdate.md) or [onNameNotPresent](yarn.unity.dialoguecharacternameview.onnamenotpresent.md) events, depending on the contents of `line` .

```csharp
public override YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Parameters

| Name                                                                          | Description                                                                                                                                                                              |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Unity.LocalizedLine](yarn.unity.localizedline.md) line                  | The line to present.                                                                                                                                                                     |
| [Yarn.Unity.LineCancellationToken](yarn.unity.linecancellationtoken.md) token | A [LineCancellationToken](yarn.unity.linecancellationtoken.md) that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line. |

## Returns

A task that completes when the dialogue view has finished showing the line to the user.
