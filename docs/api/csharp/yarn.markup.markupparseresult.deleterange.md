# DeleteRange(MarkupAttribute)

Method in [MarkupParseResult](yarn.markup.markupparseresult.md)

## Summary

Deletes an attribute from this markup.

```csharp
public readonly MarkupParseResult DeleteRange(MarkupAttribute attributeToDelete)
```

## Remarks

This method deletes the range of text covered by `attributeToDelete` , and updates the other attributes in this\
markup as follows:

* Attributes that start and end before the deleted attribute are\
  unmodified.
* Attributes that start before the deleted attribute and end inside it\
  are truncated to remove the part overlapping the deleted attribute.
* Attributes that have the same position and length as the deleted\
  attribute are deleted, if they apply to any text.
* Attributes that start and end within the deleted attribute are\
  deleted.
* Attributes that start within the deleted attribute, and end outside\
  it, have their start truncated to remove the part overlapping the\
  deleted attribute.
* Attributes that start after the deleted attribute have their start\
  point adjusted to account for the deleted text.

This method does not modify the current object. A new [MarkupParseResult](yarn.markup.markupparseresult.md) is returned.

If `attributeToDelete` is not an attribute of this[MarkupParseResult](yarn.markup.markupparseresult.md), the behaviour is undefined.

## Parameters

| Name                                                                            | Description              |
| ------------------------------------------------------------------------------- | ------------------------ |
| [Yarn.Markup.MarkupAttribute](yarn.markup.markupattribute.md) attributeToDelete | The attribute to remove. |

## Returns

A new [MarkupParseResult](yarn.markup.markupparseresult.md) object, with the\
plain text modified and an updated collection of\
attributes.
