# PaletteMarkerProcessor.ProcessReplacementMarker(MarkupAttribute,StringBuilder,List<MarkupAttribute>,string)

Method in [PaletteMarkerProcessor](/docs/api/csharp/palettemarkerprocessor.md)

## Summary


Processes a replacement marker by applying the style from the given
palette.


```csharp
public override List<LineParser.MarkupDiagnostic> ProcessReplacementMarker(MarkupAttribute marker, StringBuilder childBuilder, List<MarkupAttribute> childAttributes, string localeCode)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md) marker|The marker to process.|
|`System.Text.StringBuilder` childBuilder|A StringBuilder to build the styled text in.|
|`System.Collections.Generic.List<Yarn.Markup.MarkupAttribute>` childAttributes|An optional list of child attributes to apply, but this is ignored for TextMeshPro styles.|
|`string` localeCode|The locale code to use when formatting the style.|

## Returns

A list of markup diagnostics if there are any errors, otherwise an empty list.

