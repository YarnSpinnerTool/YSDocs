# MarkupValue

Struct in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


A value associated with a  <a href="yarn.markup.markupproperty.md">MarkupProperty</a> .


```csharp
public struct MarkupValue
```

## Remarks


You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as  <a href="yarn.dialogue.md">Dialogue</a> .


## Methods

|Name|Description|
|:---|:---|
|[ToString()](/docs/api/csharp/yarn.markup.markupvalue.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[BoolValue](/docs/api/csharp/yarn.markup.markupvalue.boolvalue.md)|Gets the bool value of this property.|
|[FloatValue](/docs/api/csharp/yarn.markup.markupvalue.floatvalue.md)|Gets the float value of this property.|
|[IntegerValue](/docs/api/csharp/yarn.markup.markupvalue.integervalue.md)|Gets the integer value of this property.|
|[StringValue](/docs/api/csharp/yarn.markup.markupvalue.stringvalue.md)|Gets the string value of this property.|
|[Type](/docs/api/csharp/yarn.markup.markupvalue.type.md)|Gets the value's type.|

## See Also

* [Dialogue.ParseMarkup\(string\)](/docs/api/csharp/yarn.dialogue.parsemarkup.md): Parses a line of text, and produces a  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  containing the results.

