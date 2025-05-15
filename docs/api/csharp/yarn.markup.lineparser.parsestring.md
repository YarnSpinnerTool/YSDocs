# LineParser.ParseString(string,string,bool)

Method in [LineParser](/docs/api/csharp/yarn.markup.lineparser.md)

## Summary


Parses a string of text and produces a markup parse result.


```csharp
public MarkupParseResult ParseString(string input, string localeCode, bool addImplicitCharacterAttribute = true)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` input|The text to parse.|
|`string` localeCode|The locale to use when processing markers, as a BCP-47 locale tag.|
| squish|If  `false` , markers that are split as part of the markup parsing process will not be re-merged before returning the result.|
| sort|If  `true` , markers will be sorted based on their position in the input.å|
|`bool` addImplicitCharacterAttribute|If true, the parser will attempt to detect a character name in the text and add a `[character]`  attribute for it.|

## Returns

A markup parse result.

