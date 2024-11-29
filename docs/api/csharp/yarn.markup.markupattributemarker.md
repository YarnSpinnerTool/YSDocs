# MarkupAttributeMarker

Struct in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


Represents a marker (e.g.  <code>[a]</code> ) in line of marked up text.


```csharp
public struct MarkupAttributeMarker
```

## Remarks


You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as  <a href="yarn.dialogue.md">Dialogue</a> .


## Methods

|Name|Description|
|:---|:---|
|[Equals(object)](/docs/api/csharp/yarn.markup.markupattributemarker.equals.md)||
|[GetHashCode()](/docs/api/csharp/yarn.markup.markupattributemarker.gethashcode.md)||
|[TryGetProperty(string,MarkupValue)](/docs/api/csharp/yarn.markup.markupattributemarker.trygetproperty.md)|Gets the property associated with the specified key, if present.|

## Properties

|Name|Description|
|:---|:---|
|[Name](/docs/api/csharp/yarn.markup.markupattributemarker.name.md)|Gets the name of the marker.|
|[Position](/docs/api/csharp/yarn.markup.markupattributemarker.position.md)|Gets the position of the marker in the plain text.|
|[Properties](/docs/api/csharp/yarn.markup.markupattributemarker.properties.md)|Gets the list of properties associated with this marker.|
|[Type](/docs/api/csharp/yarn.markup.markupattributemarker.type.md)|Gets the type of marker that this is.|

## TYPENAME_UNKNOWN_PLURAL

|Name|Description|
|:---|:---|
|[M:Yarn.Markup.MarkupAttributeMarker.op_Equality(Yarn.Markup.MarkupAttributeMarker,Yarn.Markup.MarkupAttributeMarker)~System.Boolean](/docs/api/csharp/yarn.markup.markupattributemarker.op_equality.md)||
|[M:Yarn.Markup.MarkupAttributeMarker.op_Inequality(Yarn.Markup.MarkupAttributeMarker,Yarn.Markup.MarkupAttributeMarker)~System.Boolean](/docs/api/csharp/yarn.markup.markupattributemarker.op_inequality.md)||

## See Also

* Dialogue.ParseMarkup\(string,string\)

