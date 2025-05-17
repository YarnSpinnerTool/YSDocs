# MarkupPalette

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.ScriptableObject`

## Summary


Represents a collection of marker names and colours.


```csharp
public sealed class MarkupPalette : ScriptableObject
```

## Remarks


This is intended to be used with the  [LinePresenter](yarn.unity.linepresenter.md) , and
also be a sample of using the markup system.


## Fields

|Name|Description|
|:---|:---|
|[BasicMarkers](/docs/api/csharp/yarn.unity.markuppalette.basicmarkers.md)|A list containing all the color markers defined in this palette.|
|[CustomMarkers](/docs/api/csharp/yarn.unity.markuppalette.custommarkers.md)||

## Methods

|Name|Description|
|:---|:---|
|[ColorForMarker(string,Color)](/docs/api/csharp/yarn.unity.markuppalette.colorformarker.md)|Determines the colour for a particular marker inside this palette.|
|[PaletteForMarker(string,CustomMarker)](/docs/api/csharp/yarn.unity.markuppalette.paletteformarker.md)||

## Structs

|Name|Description|
|:---|:---|
|[BasicMarker](/docs/api/csharp/yarn.unity.markuppalette.basicmarker.md)|Contains information describing the formatting style of text within a named marker.|
|[CustomMarker](/docs/api/csharp/yarn.unity.markuppalette.custommarker.md)||

