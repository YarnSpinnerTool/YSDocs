# PresentCharacter(int,TMP\_Text,CancellationToken)

Method in [TypewriterHandler](yarn.unity.typewriterhandler.md)

## Summary

Presents a single character of the line, at the appropriate point in time.

```csharp
public override async YarnTask PresentCharacter(int currentCharacterIndex, TMP_Text text, CancellationToken cancellationToken)
```

## Parameters

| Name                                                   | Description                                                    |
| ------------------------------------------------------ | -------------------------------------------------------------- |
| `int` currentCharacterIndex                            | The zero-based index of the character being displayed.         |
| `TMPro.TMP_Text` text                                  | A `TMPro.TMP_Text` object that the line is being displayed in. |
| `System.Threading.CancellationToken` cancellationToken | A cancellation token representing whether the                  |

## Returns

A task that completes when the [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md) has completed presenting this character. Dialogue views will wait until this task is complete before displaying the remainder of the line.
