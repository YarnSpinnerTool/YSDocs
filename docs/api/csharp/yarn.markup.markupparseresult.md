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
by objects that can parse markup, such as  <a href="yarn.dialogue.md">Dialogue</a> .


## Constructors

|Name|Description|
|:---|:---|
|[MarkupParseResult(string,List<MarkupAttribute>)](/docs/api/csharp/yarn.markup.markupparseresult..ctor.md)|Initializes a new instance of the  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  struct.|

## Methods

|Name|Description|
|:---|:---|
|[DeleteRange(MarkupAttribute)](/docs/api/csharp/yarn.markup.markupparseresult.deleterange.md)|Deletes an attribute from this markup.|
|[TextForAttribute(MarkupAttribute)](/docs/api/csharp/yarn.markup.markupparseresult.textforattribute.md)|Returns the substring of  <a href="yarn.markup.markupparseresult.text.md">Text</a>  covered by <code>attribute</code>  Position and Length properties.|
|[TryGetAttributeWithName(string,MarkupAttribute)](/docs/api/csharp/yarn.markup.markupparseresult.trygetattributewithname.md)|Gets the first attribute with the specified name, if present.|

## Properties

|Name|Description|
|:---|:---|
|[Attributes](/docs/api/csharp/yarn.markup.markupparseresult.attributes.md)|The list of  <a href="yarn.markup.markupattribute.md">MarkupAttribute</a> s in this parse result.|
|[Text](/docs/api/csharp/yarn.markup.markupparseresult.text.md)|The original text, with all parsed markers removed.|

## See Also

* Yarn.Markup.LineParser.ParseString\(System.String,System.String,System.Boolean,System.Boolean,System.Boolean\): 

