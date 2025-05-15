# IAttributeMarkerProcessor

Interface in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

## Summary

Provides a mechanism for producing replacement text for a
marker.

```csharp
public interface IAttributeMarkerProcessor
```

## Methods

|Name|Description|
|:---|:---|
|[ProcessReplacementMarker(MarkupAttribute,System.Text.StringBuilder,List<MarkupAttribute>,string)](/docs/api/csharp/yarn.markup.iattributemarkerprocessor.processreplacementmarker.md)|Produces replacement text for a marker.|

## See Also

* [LineParser.RegisterMarkerProcessor\(string,IAttributeMarkerProcessor\)](/docs/api/csharp/yarn.markup.lineparser.registermarkerprocessor.md): Registers an object as a marker processor for a given marker name.
* [LineParser.DeregisterMarkerProcessor\(string\)](/docs/api/csharp/yarn.markup.lineparser.deregistermarkerprocessor.md): Removes any marker processor associated with a given marker name.

