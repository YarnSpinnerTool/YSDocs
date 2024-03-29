# MarkupParseResult

Struct in [Yarn.Markup](../)

Inherits from `System.ValueType`

## Summary

The result of parsing a line of marked-up text.

```csharp
public struct MarkupParseResult
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [Dialogue](../../yarn/yarn.dialogue/) .

## Fields

| Name                                                      | Description                                                                            |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| [Attributes](yarn.markup.markupparseresult.attributes.md) | The list of [MarkupAttribute](../yarn.markup.markupattribute/) s in this parse result. |
| [Text](yarn.markup.markupparseresult.text.md)             | The original text, with all parsed markers removed.                                    |

## Methods

| Name                                                                                                        | Description                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [DeleteRange(MarkupAttribute)](yarn.markup.markupparseresult.deleterange.md)                                | Deletes an attribute from this markup.                                                                                        |
| [TextForAttribute(MarkupAttribute)](yarn.markup.markupparseresult.textforattribute.md)                      | Returns the substring of [Text](yarn.markup.markupparseresult.text.md) covered by `attribute` Position and Length properties. |
| [TryGetAttributeWithName(string,MarkupAttribute)](yarn.markup.markupparseresult.trygetattributewithname.md) | Gets the first attribute with the specified name, if present.                                                                 |

## See Also

* [Dialogue.ParseMarkup(string)](../../yarn/yarn.dialogue/yarn.dialogue.parsemarkup.md): Parses a line of text, and produces a [MarkupParseResult](./) containing the results.
