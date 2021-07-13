# MarkupAttribute Struct

Represents a range of text in a marked-up string.


```csharp
public struct MarkupAttribute
```
## Remarks

You do not create instances of this struct yourself. It is created
by objects that can parse markup, such as [`Dialogue`](/api/csharp/yarn/dialogue.md).




## Properties
|Name|Description|
|:---|:---|
|[`Length`](/api/csharp/yarn.markup/markupattribute.length.md)| Gets the number of text elements in the plain text that this attribute covers. |
|[`Name`](/api/csharp/yarn.markup/markupattribute.name.md)| Gets the name of the attribute. |
|[`Position`](/api/csharp/yarn.markup/markupattribute.position.md)| Gets the position in the plain text where this attribute begins. |
|[`Properties`](/api/csharp/yarn.markup/markupattribute.properties.md)| Gets the properties associated with this attribute. |
## Methods
|Name|Description|
|:---|:---|
|[`ToString()`](/api/csharp/yarn.markup/markupattribute.tostring.md)||
## See Also
* [`ParseMarkup(String)`](/api/csharp/yarn/dialogue.parsemarkup-system.string-.md): 
Parses a line of text, and produces a [`MarkupParseResult`](/api/csharp/yarn.markup/markupparseresult.md) containing the results.

## Namespace
[`Yarn.Markup`](/api/csharp/yarn.markup/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.Markup/MarkupParseResult.cs#L285), line 285.
