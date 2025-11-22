# ColorForMarker(string,Color)

Method in [MarkupPalette](yarn.unity.markuppalette.md)

## Summary

Determines the colour for a particular marker inside this palette.

```csharp
public bool ColorForMarker(string Marker, out Color colour)
```

## Parameters

| Name            | Description                                                                                                                      |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `string` Marker | The marker you want to get a colour for.                                                                                         |
| `Color` colour  | The colour of the marker, or `UnityEngine.Color.black` if it doesn't exist in the [MarkupPalette](yarn.unity.markuppalette.md) . |

## Returns

`true` if the marker exists within this\
palette; `false` otherwise.
