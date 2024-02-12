# MarkupProperty

Struct in [Yarn.Markup](../)

Inherits from `System.ValueType`

## Summary

A property associated with a [MarkupAttribute](../yarn.markup.markupattribute/) .

```csharp
public struct MarkupProperty
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [Dialogue](../../yarn/yarn.dialogue/) .

## Properties

| Name                                         | Description                     |
| -------------------------------------------- | ------------------------------- |
| [Name](yarn.markup.markupproperty.name.md)   | Gets the name of the property.  |
| [Value](yarn.markup.markupproperty.value.md) | Gets the value of the property. |

## See Also

* [Dialogue.ParseMarkup(string)](../../yarn/yarn.dialogue/yarn.dialogue.parsemarkup.md): Parses a line of text, and produces a [MarkupParseResult](../yarn.markup.markupparseresult/) containing the results.
