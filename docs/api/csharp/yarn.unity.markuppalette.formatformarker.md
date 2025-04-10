# FormatForMarker(string,FormatMarker)

Method in [MarkupPalette](yarn.unity.markuppalette.md)

## Summary

Gets formatting information. for a particular marker inside this palette.

```csharp
public bool FormatForMarker(string markerName, out FormatMarker palette)
```

## Parameters

| Name                                                                                      | Description                                                                                                                                               |
| ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `string` markerName                                                                       | The marker you want to get formatting information for.                                                                                                    |
| [Yarn.Unity.MarkupPalette.FormatMarker](yarn.unity.markuppalette.formatmarker.md) palette | The [FormatMarker](yarn.unity.markuppalette.formatmarker.md) for the given marker name, or a default format if a marker named `markerName` was not found. |

## Returns

`true` if the marker exists within this palette; `false` otherwise.
