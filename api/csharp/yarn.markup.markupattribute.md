# MarkupAttribute

Struct in [Yarn.Markup](/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


Represents a range of text in a marked-up string.


```csharp
public struct MarkupAttribute
```

## Remarks


You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as  <a href="yarn.dialogue.md">Dialogue</a> .


## Properties

|Name|Description|
|:---|:---|
|[Length](/api/csharp/yarn.markup.markupattribute.length.md)|Gets the number of text elements in the plain text that this attribute covers.|
|[Name](/api/csharp/yarn.markup.markupattribute.name.md)|Gets the name of the attribute.|
|[Position](/api/csharp/yarn.markup.markupattribute.position.md)|Gets the position in the plain text where this attribute begins.|
|[Properties](/api/csharp/yarn.markup.markupattribute.properties.md)|Gets the properties associated with this attribute.|

## Methods

|Name|Description|
|:---|:---|
|[ToString()](/api/csharp/yarn.markup.markupattribute.tostring.md)||

## See Also

* [Dialogue.ParseMarkup\(string)](/api/csharp/yarn.dialogue.parsemarkup.md): Parses a line of text, and produces a  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  containing the results.

