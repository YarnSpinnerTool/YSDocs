# MarkupValue

Struct in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


A value associated with a  [MarkupProperty](yarn.markup.markupproperty.md) .


```csharp
public struct MarkupValue
```

## Remarks


You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as  [LineParser](yarn.markup.lineparser.md) .


## Methods

|Name|Description|
|:---|:---|
|[ToString()](/docs/api/csharp/yarn.markup.markupvalue.tostring-1.md)||
|[ToString(IFormatProvider)](/docs/api/csharp/yarn.markup.markupvalue.tostring-2.md)||

## Properties

|Name|Description|
|:---|:---|
|[BoolValue](/docs/api/csharp/yarn.markup.markupvalue.boolvalue.md)|Gets the bool value of this property.|
|[FloatValue](/docs/api/csharp/yarn.markup.markupvalue.floatvalue.md)|Gets the float value of this property.|
|[IntegerValue](/docs/api/csharp/yarn.markup.markupvalue.integervalue.md)|Gets the integer value of this property.|
|[StringValue](/docs/api/csharp/yarn.markup.markupvalue.stringvalue.md)|Gets the string value of this property.|
|[Type](/docs/api/csharp/yarn.markup.markupvalue.type.md)|Gets the value's type.|

## See Also

* Yarn.Markup.LineParser.ParseString\(System.String,System.String,System.Boolean,System.Boolean,System.Boolean\): 

