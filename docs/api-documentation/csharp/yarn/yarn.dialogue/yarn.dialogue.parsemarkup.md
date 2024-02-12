# ParseMarkup(string)

Method in [Dialogue](./)

## Summary

Parses a line of text, and produces a [MarkupParseResult](../../yarn.markup/yarn.markup.markupparseresult/) containing the results.

```csharp
public MarkupParseResult ParseMarkup(string line)
```

## Remarks

The [MarkupParseResult](../../yarn.markup/yarn.markup.markupparseresult/) 's [Text](../../yarn.markup/yarn.markup.markupparseresult/yarn.markup.markupparseresult.text.md) will have any `select` , `plural` or `ordinal` markers replaced with the appropriate text, following this [Dialogue](./) 's [LanguageCode](yarn.dialogue.languagecode.md) .

## Parameters

| Name          | Description                |
| ------------- | -------------------------- |
| `string` line | The line of text to parse. |

## Returns

The results of parsing the markup.
