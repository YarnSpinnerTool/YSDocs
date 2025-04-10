# RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [CharacterColorView](yarn.unity.charactercolorview.md)

## Summary

Updates the text colour of `Yarn.Unity.CharacterColorView.lineTexts` based on the character name of `line` , if any.

```csharp
public override YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Remarks

If the line doesn't have a character name, or if the character name is not found in `Yarn.Unity.CharacterColorView.colorData` , `Yarn.Unity.CharacterColorView.defaultColor` is used.

## Parameters

| Name                                                                          | Description                                                                                                                                                                              |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Unity.LocalizedLine](yarn.unity.localizedline.md) line                  | The line to present.                                                                                                                                                                     |
| [Yarn.Unity.LineCancellationToken](yarn.unity.linecancellationtoken.md) token | A [LineCancellationToken](yarn.unity.linecancellationtoken.md) that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line. |

## Returns

A task that completes when the dialogue view has finished showing the line to the user.
