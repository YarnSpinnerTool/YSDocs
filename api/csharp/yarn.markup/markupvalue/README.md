# MarkupValue

A value associated with a [`MarkupProperty`](../markupproperty/).

```csharp
public struct MarkupValue
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [`Dialogue`](../../yarn/dialogue/).

## Properties

| Name | Description |
| :--- | :--- |
| [`BoolValue`](markupvalue.boolvalue.md) | Gets the bool value of this property. |
| [`FloatValue`](markupvalue.floatvalue.md) | Gets the float value of this property. |
| [`IntegerValue`](markupvalue.integervalue.md) | Gets the integer value of this property. |
| [`StringValue`](markupvalue.stringvalue.md) | Gets the string value of this property. |
| [`Type`](markupvalue.type.md) | Gets the value's type. |

## Methods

| Name | Description |
| :--- | :--- |
| [`ToString()`](markupvalue.tostring.md) |  |

## See Also

* [`ParseMarkup(String)`](../../yarn/dialogue/dialogue.parsemarkup-system.string.md): 

  Parses a line of text, and produces a [`MarkupParseResult`](../markupparseresult/) containing the results.

## Namespace

[`Yarn.Markup`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs#L418), line 418.

