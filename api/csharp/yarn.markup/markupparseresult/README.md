# MarkupParseResult

The result of parsing a line of marked-up text.

```csharp
public struct MarkupParseResult
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [`Dialogue`](../../yarn/dialogue/).

## Fields

| Name | Description |
| :--- | :--- |
| [`Attributes`](markupparseresult.attributes.md) | The list of [`MarkupAttribute`](../markupattribute/)s in this parse result. |
| [`Text`](markupparseresult.text.md) | The original text, with all parsed markers removed. |

## Methods

| Name | Description |
| :--- | :--- |
| [`DeleteRange(MarkupAttribute)`](markupparseresult.deleterange-markupattribute.md) | Deletes an attribute from this markup. |
| [`TextForAttribute(MarkupAttribute)`](markupparseresult.textforattribute-markupattribute.md) | Returns the substring of [`Text`](markupparseresult.text.md) covered by `attribute` Position and Length properties. |
| [`TryGetAttributeWithName(String, out MarkupAttribute)`](markupparseresult.trygetattributewithname-system.string-markupattribute.md) | Gets the first attribute with the specified name, if present. |

## See Also

* [`ParseMarkup(String)`](../../yarn/dialogue/dialogue.parsemarkup-system.string.md): 

  Parses a line of text, and produces a [`MarkupParseResult`](./) containing the results.

## Namespace

[`Yarn.Markup`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs#L40), line 40.

