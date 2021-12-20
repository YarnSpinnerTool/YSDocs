# ParseMarkup(string)

Method in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Parses a line of text, and produces a  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  containing the results.


```csharp
public MarkupParseResult ParseMarkup(string line)
```

## Remarks


The  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a> 's  <a href="yarn.markup.markupparseresult.text.md">Text</a>  will have any `select`,
`plural` or `ordinal` markers replaced with the appropriate
text, following this  <a href="yarn.dialogue.md">Dialogue</a> 's  <a href="yarn.dialogue.languagecode.md">LanguageCode</a> .


## Parameters

|Name|Description|
|:---|:---|
|line|The line of text to parse.|

## Returns

The results of parsing the markup.

