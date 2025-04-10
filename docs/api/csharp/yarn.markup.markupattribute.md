# MarkupAttribute

Struct in [Yarn.Markup](yarn.markup.md)

Inherits from `System.ValueType`

## Summary

Represents a range of text in a marked-up string.

```csharp
public struct MarkupAttribute
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [Dialogue](yarn.dialogue.md) .

## Methods

| Name                                                                                | Description |
| ----------------------------------------------------------------------------------- | ----------- |
| [Shift(int)](yarn.markup.markupattribute.shift.md)                                  |             |
| [ToString()](yarn.markup.markupattribute.tostring.md)                               |             |
| [TryGetProperty(string,MarkupValue)](yarn.markup.markupattribute.trygetproperty.md) |             |

## Properties

| Name                                                    | Description                                                                    |
| ------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Length](yarn.markup.markupattribute.length.md)         | Gets the number of text elements in the plain text that this attribute covers. |
| [Name](yarn.markup.markupattribute.name.md)             | Gets the name of the attribute.                                                |
| [Position](yarn.markup.markupattribute.position.md)     | Gets the position in the plain text where this attribute begins.               |
| [Properties](yarn.markup.markupattribute.properties.md) | Gets the properties associated with this attribute.                            |

## See Also

* Dialogue.ParseMarkup(string,string)
