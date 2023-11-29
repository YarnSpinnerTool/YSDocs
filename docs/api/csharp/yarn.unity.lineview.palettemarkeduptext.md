# LineView.PaletteMarkedUpText(Markup.MarkupParseResult,MarkupPalette)

Method in [LineView](/api/csharp/yarn.unity.lineview.md)

## Summary


Applies the  <code>palette</code>  to the line based on it's markup.


```csharp
public static string PaletteMarkedUpText(Markup.MarkupParseResult line, MarkupPalette palette)
```

## Remarks


This is static so that other dialogue views can reuse this code.
While this is simplistic it is useful enough that multiple pieces might well want it.


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupParseResult](/api/csharp/yarn.markup.markupparseresult.md) line|The parsed marked up line with it's attributes.|
|[Yarn.Unity.MarkupPalette](/api/csharp/yarn.unity.markuppalette.md) palette|The palette mapping attributes to colours.|

## Returns

A TMP formatted string with the palette markup values injected within.

