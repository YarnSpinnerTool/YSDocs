# MarkupPalette

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `UnityEngine.ScriptableObject`

## Summary

Represents a collection of marker names and colours.

```csharp
public sealed class MarkupPalette : ScriptableObject
```

## Remarks

This is intended to be used with the [LinePresenter](yarn.unity.linepresenter.md) , and\
also be a sample of using the markup system.

## Fields

| Name                                                       | Description                                                      |
| ---------------------------------------------------------- | ---------------------------------------------------------------- |
| [BasicMarkers](yarn.unity.markuppalette.basicmarkers.md)   | A list containing all the color markers defined in this palette. |
| [CustomMarkers](yarn.unity.markuppalette.custommarkers.md) |                                                                  |

## Methods

| Name                                                                                  | Description                                                        |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| [ColorForMarker(string,Color)](yarn.unity.markuppalette.colorformarker.md)            | Determines the colour for a particular marker inside this palette. |
| [PaletteForMarker(string,CustomMarker)](yarn.unity.markuppalette.paletteformarker.md) |                                                                    |

## Structs

| Name                                                     | Description                                                                         |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [BasicMarker](yarn.unity.markuppalette.basicmarker.md)   | Contains information describing the formatting style of text within a named marker. |
| [CustomMarker](yarn.unity.markuppalette.custommarker.md) |                                                                                     |
