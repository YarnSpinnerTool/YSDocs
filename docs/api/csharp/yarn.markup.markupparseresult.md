# MarkupParseResult

Struct in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


The result of parsing a line of marked-up text.


```csharp
public struct MarkupParseResult
```

## Remarks


You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as  [Dialogue](yarn.dialogue.md) .


## Constructors

|Name|Description|
|:---|:---|
|[MarkupParseResult(string,List<MarkupAttribute>)](/docs/api/csharp/yarn.markup.markupparseresult..ctor.md)|Initializes a new instance of the  [MarkupParseResult](yarn.markup.markupparseresult.md)  struct.|

## Methods

|Name|Description|
|:---|:---|
|[DeleteRange(MarkupAttribute)](/docs/api/csharp/yarn.markup.markupparseresult.deleterange.md)|Deletes an attribute from this markup.|
|[TextForAttribute(MarkupAttribute)](/docs/api/csharp/yarn.markup.markupparseresult.textforattribute.md)|Returns the substring of  [Text](yarn.markup.markupparseresult.text.md)  covered by `attribute`  Position and Length properties.|
|[TryGetAttributeWithName(string,MarkupAttribute)](/docs/api/csharp/yarn.markup.markupparseresult.trygetattributewithname.md)|Gets the first attribute with the specified name, if present.|

## Properties

|Name|Description|
|:---|:---|
|[Attributes](/docs/api/csharp/yarn.markup.markupparseresult.attributes.md)|The list of  [MarkupAttribute](yarn.markup.markupattribute.md) s in this parse result.|
|[Text](/docs/api/csharp/yarn.markup.markupparseresult.text.md)|The original text, with all parsed markers removed.|

## See Also

* Yarn.Markup.LineParser.ParseString\(System.String,System.String,System.Boolean,System.Boolean,System.Boolean\): 

