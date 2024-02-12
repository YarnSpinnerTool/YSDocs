# MarkupValue

Struct in [Yarn.Markup](../)

Inherits from `System.ValueType`

## Summary

A value associated with a [MarkupProperty](../yarn.markup.markupproperty/) .

```csharp
public struct MarkupValue
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [Dialogue](../../yarn/yarn.dialogue/) .

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

* [Dialogue.ParseMarkup(string)](../../yarn/yarn.dialogue/yarn.dialogue.parsemarkup.md): Parses a line of text, and produces a [MarkupParseResult](../yarn.markup.markupparseresult/) containing the results.
