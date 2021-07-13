# MarkupParseResult.DeleteRange Method

Deletes an attribute from this markup.


```csharp
public MarkupParseResult DeleteRange(MarkupAttribute attributeToDelete)
```
## Remarks

This method deletes the range of text covered by <code data-dev-comment-type="paramref" class="paramref">attributeToDelete</code>, and updates the other attributes in
this markup as follows:

- Attributes that start and end before the deleted attribute
are unmodified.

- Attributes that start before the deleted attribute and end
inside it are truncated to remove the part overlapping the
deleted attribute.

- Attributes that have the same position and length as the
deleted attribute are deleted, if they apply to any text.

- Attributes that start and end within the deleted attribute
are deleted.

- Attributes that start within the deleted attribute, and end
outside it, have their start truncated to remove the part
overlapping the deleted attribute.

- Attributes that start after the deleted attribute have their
start point adjusted to account for the deleted text.

This method does not modify the current object. A new
MarkupParseResult is returned.

If <code data-dev-comment-type="paramref" class="paramref">attributeToDelete</code> is not an attribute of
this [`MarkupParseResult`](/api/csharp/yarn.markup/markupparseresult.md), the behaviour is
undefined.


## Parameters
|Parameter|Description|
|:---|:---|
|[`MarkupAttribute`](/api/csharp/yarn.markup/markupattribute.md) attributeToDelete|The attribute to remove.|
## Return Type
[`MarkupParseResult`](/api/csharp/yarn.markup/markupparseresult.md): A new MarkupParseResult, with the plain text modified
and an updated collection of attributes.



<div class="class-metadata">

Parent: [`MarkupParseResult`](/api/csharp/yarn.markup/markupparseresult.md), Namespace: [`Yarn.Markup`](/api/csharp/yarn.markup/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs#L166), line 166.
