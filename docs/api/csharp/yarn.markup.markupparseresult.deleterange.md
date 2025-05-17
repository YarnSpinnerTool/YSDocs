# MarkupParseResult.DeleteRange(MarkupAttribute)

Method in [MarkupParseResult](/docs/api/csharp/yarn.markup.markupparseresult.md)

## Summary


Deletes an attribute from this markup.


```csharp
public readonly MarkupParseResult DeleteRange(MarkupAttribute attributeToDelete)
```

## Remarks


This method deletes the range of text covered by  `attributeToDelete` , and updates the other attributes in this
markup as follows:

<ul type="bullet">
<li>
Attributes that start and end before the deleted attribute are
unmodified.
</li>
<li>
Attributes that start before the deleted attribute and end inside it
are truncated to remove the part overlapping the deleted attribute.
</li>
<li>
Attributes that have the same position and length as the deleted
attribute are deleted, if they apply to any text.
</li>
<li>
Attributes that start and end within the deleted attribute are
deleted.
</li>
<li>
Attributes that start within the deleted attribute, and end outside
it, have their start truncated to remove the part overlapping the
deleted attribute.
</li>
<li>
Attributes that start after the deleted attribute have their start
point adjusted to account for the deleted text.
</li>
</ul> <p>
This method does not modify the current object. A new <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a> is returned.
</p> <p>
If `attributeToDelete` is not an attribute of this
<a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>, the behaviour is undefined.
</p>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md) attributeToDelete|The attribute to remove.|

## Returns

A new  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  object, with the
plain text modified and an updated collection of
attributes.

