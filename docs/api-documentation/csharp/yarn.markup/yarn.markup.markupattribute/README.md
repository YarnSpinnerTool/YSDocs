# MarkupAttribute

Struct in [Yarn.Markup](../)

Inherits from `System.ValueType`

## Summary

Represents a range of text in a marked-up string.

```csharp
public struct MarkupAttribute
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [Dialogue](../../yarn/yarn.dialogue/) .

## Methods

| Name                                                  | Description |
| ----------------------------------------------------- | ----------- |
| [ToString()](yarn.markup.markupattribute.tostring.md) |             |

## Properties

| Name                                                    | Description                                                                    |
| ------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Length](yarn.markup.markupattribute.length.md)         | Gets the number of text elements in the plain text that this attribute covers. |
| [Name](yarn.markup.markupattribute.name.md)             | Gets the name of the attribute.                                                |
| [Position](yarn.markup.markupattribute.position.md)     | Gets the position in the plain text where this attribute begins.               |
| [Properties](yarn.markup.markupattribute.properties.md) | Gets the properties associated with this attribute.                            |

## See Also

* [Dialogue.ParseMarkup(string)](../../yarn/yarn.dialogue/yarn.dialogue.parsemarkup.md): Parses a line of text, and produces a [MarkupParseResult](../yarn.markup.markupparseresult/) containing the results.
