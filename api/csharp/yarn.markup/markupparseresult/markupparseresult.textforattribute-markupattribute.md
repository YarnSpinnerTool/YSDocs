# TextForAttribute\(MarkupAttribute\)

Returns the substring of [`Text`](markupparseresult.text.md) covered by `attribute` Position and Length properties.

```csharp
public string TextForAttribute(MarkupAttribute attribute)
```

## Remarks

If the attribute's [`Length`](../markupattribute/markupattribute.length.md) property is zero, this method returns the empty string.

This method does not check to see if `attribute` is an attribute belonging to this MarkupParseResult. As a result, if you pass an attribute that doesn't belong, it may describe a range of text that does not appear in [`Text`](markupparseresult.text.md). If this occurs, an [`IndexOutOfRangeException`](https://docs.microsoft.com/dotnet/api/System.IndexOutOfRangeException) will be thrown.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`MarkupAttribute`](../markupattribute/) attribute | The attribute to get the text for. |

## Return Type

[`string`](https://docs.microsoft.com/dotnet/api/System.String): The text contained within the attribute.

## Namespace

[`Yarn.Markup`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs#L112), line 112.

