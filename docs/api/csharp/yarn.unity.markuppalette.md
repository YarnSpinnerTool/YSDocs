# MarkupPalette

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `UnityEngine.ScriptableObject`

## Summary

Represents a collection of marker names and colours.

```csharp
public class MarkupPalette : ScriptableObject
```

## Remarks

This is intended to be used with the LineView, and also be a sample of using the markup system.

## Fields

| Name                                                       | Description                                                      |
| ---------------------------------------------------------- | ---------------------------------------------------------------- |
| [FormatMarkers](yarn.unity.markuppalette.formatmarkers.md) | A list containing all the color markers defined in this palette. |

## Methods

| Name                                                                                | Description                                                               |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| [ColorForMarker(string,Color)](yarn.unity.markuppalette.colorformarker.md)          | Determines the colour for a particular marker inside this palette.        |
| [FormatForMarker(string,FormatMarker)](yarn.unity.markuppalette.formatformarker.md) | Gets formatting information. for a particular marker inside this palette. |

## Structs

| Name                                                     | Description                                                                         |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [FormatMarker](yarn.unity.markuppalette.formatmarker.md) | Contains information describing the formatting style of text within a named marker. |
