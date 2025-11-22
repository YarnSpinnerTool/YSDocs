# MarkupPalette.ColorForMarker(string,Color)

Method in [MarkupPalette](/docs/api/csharp/yarn.unity.markuppalette.md)

## Summary


Determines the colour for a particular marker inside this palette.


```csharp
public bool ColorForMarker(string Marker, out Color colour)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` Marker|The marker you want to get a colour for.|
|`Color` colour|The colour of the marker, or  <code>UnityEngine.Color.black</code>  if it doesn't exist in the  <a href="yarn.unity.markuppalette.md">MarkupPalette</a> .|

## Returns

<code>true</code>  if the marker exists within this
palette;  <code>false</code>  otherwise.

