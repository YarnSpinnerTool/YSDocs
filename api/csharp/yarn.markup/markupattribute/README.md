# MarkupAttribute

Represents a range of text in a marked-up string.

```csharp
public struct MarkupAttribute
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [`Dialogue`](../../yarn/dialogue/).

## Properties

| Name | Description |
| :--- | :--- |
| [`Length`](markupattribute.length.md) | Gets the number of text elements in the plain text that this attribute covers. |
| [`Name`](markupattribute.name.md) | Gets the name of the attribute. |
| [`Position`](markupattribute.position.md) | Gets the position in the plain text where this attribute begins. |
| [`Properties`](markupattribute.properties.md) | Gets the properties associated with this attribute. |

## Methods

| Name | Description |
| :--- | :--- |
| [`ToString()`](markupattribute.tostring.md) |  |

## See Also

* [`ParseMarkup(String)`](../../yarn/dialogue/dialogue.parsemarkup-system.string.md): 

  Parses a line of text, and produces a [`MarkupParseResult`](../markupparseresult/) containing the results.

## Namespace

[`Yarn.Markup`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs#L285), line 285.

