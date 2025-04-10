# TextForAttribute(MarkupAttribute)

Method in [MarkupParseResult](yarn.markup.markupparseresult.md)

## Summary

Returns the substring of [Text](yarn.markup.markupparseresult.text.md) covered by `attribute` Position and Length properties.

```csharp
public string TextForAttribute(MarkupAttribute attribute)
```

## Remarks

If the attribute's [Length](yarn.markup.markupattribute.length.md) property is zero, this method returns the empty string.

This method does not check to see if `attribute` is an attribute belonging to this MarkupParseResult. As a result, if you pass an attribute that doesn't belong, it may describe a range of text that does not appear in [Text](yarn.markup.markupparseresult.text.md). If this occurs, an `System.IndexOutOfRangeException` will be thrown.

## Parameters

| Name                                                                    | Description                        |
| ----------------------------------------------------------------------- | ---------------------------------- |
| [Yarn.Markup.MarkupAttribute](yarn.markup.markupattribute.md) attribute | The attribute to get the text for. |

## Returns

The text contained within the attribute.
