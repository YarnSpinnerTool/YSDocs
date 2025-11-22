# IAttributeMarkerProcessor

Interface in [Yarn.Markup](yarn.markup.md)

## Summary

Provides a mechanism for producing replacement text for a\
marker.

```csharp
public interface IAttributeMarkerProcessor
```

## Methods

| Name                                                                                                                                                 | Description                             |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| [ProcessReplacementMarker(MarkupAttribute,System.Text.StringBuilder,List,string)](yarn.markup.iattributemarkerprocessor.processreplacementmarker.md) | Produces replacement text for a marker. |

## See Also

* [LineParser.RegisterMarkerProcessor(string,IAttributeMarkerProcessor)](yarn.markup.lineparser.registermarkerprocessor.md): Registers an object as a marker processor for a given marker name.
* [LineParser.DeregisterMarkerProcessor(string)](yarn.markup.lineparser.deregistermarkerprocessor.md): Removes any marker processor associated with a given marker name.
