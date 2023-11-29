# MarkupParseResult

Struct in [Yarn.Markup](/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


The result of parsing a line of marked-up text.


```csharp
public struct MarkupParseResult
```

## Remarks


You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as  <a href="yarn.dialogue.md">Dialogue</a> .


## Fields

|Name|Description|
|:---|:---|
|[Attributes](/api/csharp/yarn.markup.markupparseresult.attributes.md)|The list of  <a href="yarn.markup.markupattribute.md">MarkupAttribute</a> s in this parse result.|
|[Text](/api/csharp/yarn.markup.markupparseresult.text.md)|The original text, with all parsed markers removed.|

## Methods

|Name|Description|
|:---|:---|
|[DeleteRange(MarkupAttribute)](/api/csharp/yarn.markup.markupparseresult.deleterange.md)|Deletes an attribute from this markup.|
|[TextForAttribute(MarkupAttribute)](/api/csharp/yarn.markup.markupparseresult.textforattribute.md)|Returns the substring of  <a href="yarn.markup.markupparseresult.text.md">Text</a>  covered by <code>attribute</code>  Position and Length properties.|
|[TryGetAttributeWithName(string,MarkupAttribute)](/api/csharp/yarn.markup.markupparseresult.trygetattributewithname.md)|Gets the first attribute with the specified name, if present.|

## See Also

* [Dialogue.ParseMarkup\(string\)](/api/csharp/yarn.dialogue.parsemarkup.md): Parses a line of text, and produces a  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  containing the results.

