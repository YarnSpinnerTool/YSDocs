# ParseMarkup(string)

Method in [Dialogue](yarn.dialogue.md)

## Summary

Parses a line of text, and produces a [MarkupParseResult](yarn.markup.markupparseresult.md) containing the results.

```csharp
public MarkupParseResult ParseMarkup(string line)
```

## Remarks

The [MarkupParseResult](yarn.markup.markupparseresult.md) 's [Text](yarn.markup.markupparseresult.text.md) will have any `select` , `plural` or `ordinal` markers replaced with the appropriate text, following this [Dialogue](yarn.dialogue.md) 's [LanguageCode](yarn.dialogue.languagecode.md) .

## Parameters

| Name          | Description                |
| ------------- | -------------------------- |
| `string` line | The line of text to parse. |

## Returns

The results of parsing the markup.
