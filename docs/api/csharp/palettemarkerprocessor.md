# PaletteMarkerProcessor

Inherits from [`ReplacementMarkupHandler`](/docs/api/csharp/yarn.unity.replacementmarkuphandler.md)

## Summary


An attribute marker processor that uses a  [MarkupPalette](yarn.unity.markuppalette.md)  to
apply TextMeshPro styling tags to a line.


```csharp
public sealed class PaletteMarkerProcessor : Yarn.Unity.ReplacementMarkupHandler
```

## Remarks

This marker processor registers itself as a handler for markers
whose name is equal to the name of a style in the given palette. For
example, if the palette defines a style named "happy", this marker processor
will process tags in a Yarn line named  `[happy]`  by inserting the
appropriate TextMeshProp style tags defined for the "happy" style.

## Fields

|Name|Description|
|:---|:---|
|[lineProvider](/docs/api/csharp/palettemarkerprocessor.lineprovider.md)|The line provider to register this markup processor with.|
|[palette](/docs/api/csharp/palettemarkerprocessor.palette.md)|The  [MarkupPalette](yarn.unity.markuppalette.md)  to use when applying styles.|

## Methods

|Name|Description|
|:---|:---|
|[ProcessReplacementMarker(MarkupAttribute,StringBuilder,List<MarkupAttribute>,string)](/docs/api/csharp/palettemarkerprocessor.processreplacementmarker.md)|Processes a replacement marker by applying the style from the given palette.|

