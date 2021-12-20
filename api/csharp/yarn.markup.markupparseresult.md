# MarkupParseResult

Struct in [Yarn.Markup](/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


The result of parsing a line of marked-up text.


```csharp
public struct MarkupParseResult
    {
    }
```

## Fields

|Name|Description|
|:---|:---|
|[Text](/api/csharp/yarn.markup.markupparseresult.text.md)|The original text, with all parsed markers removed.|
|[Attributes](/api/csharp/yarn.markup.markupparseresult.attributes.md)|The list of  <a href="yarn.markup.markupattribute.md">MarkupAttribute</a> s in this parse result.|

## Methods

|Name|Description|
|:---|:---|
|[TryGetAttributeWithName(string,MarkupAttribute)](/api/csharp/yarn.markup.markupparseresult.trygetattributewithname.md)|Gets the first attribute with the specified name, if present.|
|[TextForAttribute(MarkupAttribute)](/api/csharp/yarn.markup.markupparseresult.textforattribute.md)|Returns the substring of  <a href="yarn.markup.markupparseresult.text.md">Text</a>  covered by <code>attribute</code>  Position and Length properties.|
|[DeleteRange(MarkupAttribute)](/api/csharp/yarn.markup.markupparseresult.deleterange.md)|Deletes an attribute from this markup.|

