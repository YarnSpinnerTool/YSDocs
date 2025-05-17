# LineParser.RegisterMarkerProcessor(string,IAttributeMarkerProcessor)

Method in [LineParser](/docs/api/csharp/yarn.markup.lineparser.md)

## Summary

Registers an object as a marker processor for a given
marker name.

```csharp
public void RegisterMarkerProcessor(string attributeName, IAttributeMarkerProcessor markerProcessor)
```

## Remarks


When a marker processor is registered for a marker name, the
parser will ask the processor for text to insert into the plain
text. This allows users of the  <a href="yarn.markup.lineparser.md">LineParser</a>  class
to dynamically replace text in a line. The  <code>nomarkup</code>  tag is
implemented in this way by the  <a href="yarn.markup.lineparser.md">LineParser</a>  class
directly; the  <a href="yarn.dialogue.md">Dialogue</a>  class uses this mechanism
to implement the  <code>select</code> ,  <code>plural</code>  and  <code>ordinal</code>  markers.


## Parameters

|Name|Description|
|:---|:---|
|`string` attributeName|The name of the marker that should use this marker processor.|
|[Yarn.Markup.IAttributeMarkerProcessor](/docs/api/csharp/yarn.markup.iattributemarkerprocessor.md) markerProcessor|The object that should be invoked when markers with this name are encountered.|

