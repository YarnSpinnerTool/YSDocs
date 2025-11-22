# IAttributeMarkerProcessor.ProcessReplacementMarker(MarkupAttribute,System.Text.StringBuilder,List<MarkupAttribute>,string)

Method in [IAttributeMarkerProcessor](/docs/api/csharp/yarn.markup.iattributemarkerprocessor.md)

## Summary


Produces replacement text for a marker.


```csharp
public ReplacementMarkerResult ProcessReplacementMarker(MarkupAttribute marker, System.Text.StringBuilder childBuilder, List<MarkupAttribute> childAttributes, string localeCode);
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md) marker|The marker to process into replacement text.|
|`System.Text.StringBuilder` childBuilder|A  <code>System.Text.StringBuilder</code>  that contains the child text contained within  <code>marker</code> . Use the methods on this stringbuilder to produce any text needed from this marker.|
|`System.Collections.Generic.List<Yarn.Markup.MarkupAttribute>` childAttributes|The child attributes of  <code>marker</code> .|
|`string` localeCode|A BCP-47 locale code that represents the locale in which any processing should take place.|

## Returns

The collection of diagnostics produced during processing,
and the number of invisible characters created during processing.

