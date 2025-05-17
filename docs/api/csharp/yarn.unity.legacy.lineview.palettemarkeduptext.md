# LineView.PaletteMarkedUpText(Markup.MarkupParseResult,MarkupPalette,bool)

Method in [LineView](/docs/api/csharp/yarn.unity.legacy.lineview.md)

## Summary


Applies the  `palette`  to the line based on it's
markup.


```csharp
public static string PaletteMarkedUpText(Markup.MarkupParseResult line, MarkupPalette palette, bool applyLineBreaks = true)
```

## Remarks


This is static so that other dialogue views can reuse this code.
While this is simplistic it is useful enough that multiple pieces
might well want it.


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupParseResult](/docs/api/csharp/yarn.markup.markupparseresult.md) line|The parsed marked up line with it's attributes.|
|[Yarn.Unity.MarkupPalette](/docs/api/csharp/yarn.unity.markuppalette.md) palette|The palette mapping attributes to colours.|
|`bool` applyLineBreaks|If the [br /] marker is found in the line should this be replaced with a line break?|

## Returns

A TMP formatted string with the palette markup values
injected within.

