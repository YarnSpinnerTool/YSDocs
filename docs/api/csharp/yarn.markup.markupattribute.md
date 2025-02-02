# MarkupAttribute

Struct in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


Represents a range of text in a marked-up string.


```csharp
public struct MarkupAttribute
```

## Remarks


You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as  <a href="yarn.dialogue.md">Dialogue</a> .


## Methods

|Name|Description|
|:---|:---|
|[Shift(int)](/docs/api/csharp/yarn.markup.markupattribute.shift.md)||
|[ToString()](/docs/api/csharp/yarn.markup.markupattribute.tostring.md)||
|[TryGetProperty(string,MarkupValue)](/docs/api/csharp/yarn.markup.markupattribute.trygetproperty.md)||

## Properties

|Name|Description|
|:---|:---|
|[Length](/docs/api/csharp/yarn.markup.markupattribute.length.md)|Gets the number of text elements in the plain text that this attribute covers.|
|[Name](/docs/api/csharp/yarn.markup.markupattribute.name.md)|Gets the name of the attribute.|
|[Position](/docs/api/csharp/yarn.markup.markupattribute.position.md)|Gets the position in the plain text where this attribute begins.|
|[Properties](/docs/api/csharp/yarn.markup.markupattribute.properties.md)|Gets the properties associated with this attribute.|

## See Also

* Dialogue.ParseMarkup\(string,string\)

