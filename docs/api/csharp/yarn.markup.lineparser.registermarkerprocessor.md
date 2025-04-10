# RegisterMarkerProcessor(string,IAttributeMarkerProcessor)

Method in [LineParser](yarn.markup.lineparser.md)

## Summary

Registers an object as a marker processor for a given marker name.

```csharp
public void RegisterMarkerProcessor(string attributeName, IAttributeMarkerProcessor markerProcessor)
```

## Remarks

When a marker processor is registered for a marker name, the parser will ask the processor for text to insert into the plain text. This allows users of the [LineParser](yarn.markup.lineparser.md) class to dynamically replace text in a line. The `nomarkup` tag is implemented in this way by the [LineParser](yarn.markup.lineparser.md) class directly; the [Dialogue](yarn.dialogue.md) class uses this mechanism to implement the `select` , `plural` and `ordinal` markers.

## Parameters

| Name                                                                                              | Description                                                                    |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| `string` attributeName                                                                            | The name of the marker that should use this marker processor.                  |
| [Yarn.Markup.IAttributeMarkerProcessor](yarn.markup.iattributemarkerprocessor.md) markerProcessor | The object that should be invoked when markers with this name are encountered. |
