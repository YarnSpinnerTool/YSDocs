# MarkupAttribute

Struct in [Yarn.Markup](/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


Represents a range of text in a marked-up string.


```csharp
public struct MarkupAttribute
    {
    }
```

## Remarks


You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as  <a href="yarn.dialogue.md">Dialogue</a> .


## See Also

* [ParseMarkup(string)](/api/csharp/yarn.dialogue.parsemarkup.md)

## Properties

|Name|Description|
|:---|:---|
|[Position](/api/csharp/yarn.markup.markupattribute.position.md)|Gets the position in the plain text where this attribute begins.|
|[Length](/api/csharp/yarn.markup.markupattribute.length.md)|Gets the number of text elements in the plain text that this attribute covers.|
|[Name](/api/csharp/yarn.markup.markupattribute.name.md)|Gets the name of the attribute.|
|[Properties](/api/csharp/yarn.markup.markupattribute.properties.md)|Gets the properties associated with this attribute.|

## Methods

|Name|Description|
|:---|:---|
|[ToString()](/api/csharp/yarn.markup.markupattribute.tostring.md)||

