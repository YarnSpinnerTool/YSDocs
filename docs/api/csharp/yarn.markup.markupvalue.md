# MarkupValue

Struct in [Yarn.Markup](yarn.markup.md)

Inherits from `System.ValueType`

## Summary

A value associated with a [MarkupProperty](yarn.markup.markupproperty.md) .

```csharp
public struct MarkupValue
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [Dialogue](yarn.dialogue.md) .

## Methods

| Name                                              | Description |
| ------------------------------------------------- | ----------- |
| [ToString()](yarn.markup.markupvalue.tostring.md) |             |

## Properties

| Name                                                    | Description                              |
| ------------------------------------------------------- | ---------------------------------------- |
| [BoolValue](yarn.markup.markupvalue.boolvalue.md)       | Gets the bool value of this property.    |
| [FloatValue](yarn.markup.markupvalue.floatvalue.md)     | Gets the float value of this property.   |
| [IntegerValue](yarn.markup.markupvalue.integervalue.md) | Gets the integer value of this property. |
| [StringValue](yarn.markup.markupvalue.stringvalue.md)   | Gets the string value of this property.  |
| [Type](yarn.markup.markupvalue.type.md)                 | Gets the value's type.                   |

## See Also

* [Dialogue.ParseMarkup(string)](yarn.dialogue.parsemarkup.md): Parses a line of text, and produces a [MarkupParseResult](yarn.markup.markupparseresult.md) containing the results.
