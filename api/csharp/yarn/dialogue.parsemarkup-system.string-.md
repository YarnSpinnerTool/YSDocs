# Dialogue.ParseMarkup Method

Parses a line of text, and produces a [`MarkupParseResult`](/api/csharp/yarn.markup/markupparseresult.md) containing the results.


```csharp
public MarkupParseResult ParseMarkup(string line)
```
## Remarks

The [`MarkupParseResult`](/api/csharp/yarn.markup/markupparseresult.md)'s [`Text`](/api/csharp/yarn.markup/markupparseresult.text.md) will have any `select`,
`plural` or `ordinal` markers replaced with the appropriate
text, following this [`Dialogue`](/api/csharp/yarn/dialogue.md)'s [`LanguageCode`](/api/csharp/yarn/dialogue.languagecode.md).


## Parameters
|Parameter|Description|
|:---|:---|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) line|The line of text to parse.|
## Return Type
[`MarkupParseResult`](/api/csharp/yarn.markup/markupparseresult.md): The results of parsing the markup.



## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L875), line 875.
