# MarkupPalette.FormatForMarker(string,FormatMarker)

Method in [MarkupPalette](/docs/api/csharp/yarn.unity.markuppalette.md)

## Summary


Gets formatting information. for a particular marker inside this
palette.


```csharp
public bool FormatForMarker(string markerName, out FormatMarker palette)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` markerName|The marker you want to get formatting information for.|
|[Yarn.Unity.MarkupPalette.FormatMarker](/docs/api/csharp/yarn.unity.markuppalette.formatmarker.md) palette|The  <a href="yarn.unity.markuppalette.formatmarker.md">FormatMarker</a>  for the given marker name, or a default format if a marker named  <code>markerName</code>  was not found.|

## Returns

<code>true</code>  if the marker exists within this
palette;  <code>false</code>  otherwise.

