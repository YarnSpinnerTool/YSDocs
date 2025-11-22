# OnLineDisplayBegin(MarkupParseResult,TMP\_Text)

Method in [IActionMarkupHandler](yarn.unity.iactionmarkuphandler.md)

## Summary

Called immediately before the first character in the line is\
presented.

```csharp
public void OnLineDisplayBegin(MarkupParseResult line, TMP_Text text);
```

## Parameters

| Name                                                       | Description                                                    |
| ---------------------------------------------------------- | -------------------------------------------------------------- |
| [MarkupParseResult](yarn.markup.markupparseresult.md) line | The line being presented.                                      |
| `TMP_Text` text                                            | A `TMPro.TMP_Text` object that the line is being displayed in. |
