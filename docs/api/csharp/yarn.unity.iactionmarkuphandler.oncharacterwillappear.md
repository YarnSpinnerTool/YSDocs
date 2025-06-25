# OnCharacterWillAppear(int,MarkupParseResult,CancellationToken)

Method in [IActionMarkupHandler](yarn.unity.iactionmarkuphandler.md)

## Summary

Called repeatedly for each visible character in the line.

```csharp
public YarnTask OnCharacterWillAppear(int currentCharacterIndex, MarkupParseResult line, CancellationToken cancellationToken);
```

## Remarks

This method is a [ActionMarkupHandler](yarn.unity.actionmarkuphandler.md)\
object's main opportunity to take action during line\
display.

## Parameters

| Name                                                       | Description                                                    |
| ---------------------------------------------------------- | -------------------------------------------------------------- |
| `int` currentCharacterIndex                                | The zero-based index of the character being displayed.         |
| text                                                       | A `TMPro.TMP_Text` object that the line is being displayed in. |
| `CancellationToken` cancellationToken                      | A cancellation token representing whether the                  |
| [MarkupParseResult](yarn.markup.markupparseresult.md) line |                                                                |

## Returns

A task that completes when the [ActionMarkupHandler](yarn.unity.actionmarkuphandler.md) has completed presenting this\
character. Dialogue presenters will wait until this task is complete\
before displaying the remainder of the line.
