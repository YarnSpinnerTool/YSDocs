# MarkupProperty

A property associated with a [`MarkupAttribute`](../markupattribute/).

```csharp
public struct MarkupProperty
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [`Dialogue`](../../yarn/dialogue/).

## Properties

| Name | Description |
| :--- | :--- |
| [`Name`](markupproperty.name.md) | Gets the name of the property. |
| [`Value`](markupproperty.value.md) | Gets the value of the property. |

## See Also

* [`ParseMarkup(String)`](../../yarn/dialogue/dialogue.parsemarkup-system.string.md): 

  Parses a line of text, and produces a [`MarkupParseResult`](../markupparseresult/) containing the results.

## Namespace

[`Yarn.Markup`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs#L385), line 385.

