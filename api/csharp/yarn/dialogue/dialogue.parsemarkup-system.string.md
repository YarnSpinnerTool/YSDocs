# ParseMarkup\(String\)

Parses a line of text, and produces a [`MarkupParseResult`](../../yarn.markup/markupparseresult/) containing the results.

```csharp
public MarkupParseResult ParseMarkup(string line)
```

## Remarks

The [`MarkupParseResult`](../../yarn.markup/markupparseresult/)'s [`Text`](../../yarn.markup/markupparseresult/markupparseresult.text.md) will have any `select`, `plural` or `ordinal` markers replaced with the appropriate text, following this [`Dialogue`](./)'s [`LanguageCode`](dialogue.languagecode.md).

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) line | The line of text to parse. |

## Return Type

[`MarkupParseResult`](../../yarn.markup/markupparseresult/): The results of parsing the markup.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L875), line 875.

