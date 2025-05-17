# MarkupAttribute

Struct in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


Represents a range of text in a marked-up string.


```csharp
public struct MarkupAttribute
```

## Remarks


You do not create instances of this struct yourself. It is created by
objects that can parse markup, such as  <a href="yarn.markup.lineparser.md">LineParser</a> .


## Methods

|Name|Description|
|:---|:---|
|[Shift(int)](/docs/api/csharp/yarn.markup.markupattribute.shift.md)|Creates a new  <a href="yarn.markup.markupattribute.md">MarkupAttribute</a>  based on the current instance whose  <a href="yarn.markup.markupattribute.position.md">Position</a>  is shifted towards the end of the string by  `shift`  characters.|
|[ToString()](/docs/api/csharp/yarn.markup.markupattribute.tostring.md)||
|[TryGetProperty(string,bool)](/docs/api/csharp/yarn.markup.markupattribute.trygetproperty-5.md)|Gets a boolean property named  `name`  from this attribute, if present.|
|[TryGetProperty(string,int)](/docs/api/csharp/yarn.markup.markupattribute.trygetproperty-3.md)|Gets an integer property named  `name`  from this attribute, if present.|
|[TryGetProperty(string,float)](/docs/api/csharp/yarn.markup.markupattribute.trygetproperty-2.md)|Gets a float property named  `name`  from this attribute, if present.|
|[TryGetProperty(string,string?)](/docs/api/csharp/yarn.markup.markupattribute.trygetproperty-4.md)|Gets a string property named  `name`  from this attribute, if present.|
|[TryGetProperty(string,MarkupValue)](/docs/api/csharp/yarn.markup.markupattribute.trygetproperty-1.md)|Gets a property named  `name`  from this attribute, if present.|

## Properties

|Name|Description|
|:---|:---|
|[Length](/docs/api/csharp/yarn.markup.markupattribute.length.md)|Gets the number of text elements in the plain text that this attribute covers.|
|[Name](/docs/api/csharp/yarn.markup.markupattribute.name.md)|Gets the name of the attribute.|
|[Position](/docs/api/csharp/yarn.markup.markupattribute.position.md)|Gets the position in the plain text where this attribute begins.|
|[Properties](/docs/api/csharp/yarn.markup.markupattribute.properties.md)|Gets the properties associated with this attribute.|

## See Also

* Yarn.Markup.LineParser.ParseString\(System.String,System.String,System.Boolean,System.Boolean,System.Boolean\): 

