# BuiltInMarkupReplacer.ProcessReplacementMarker(MarkupAttribute,StringBuilder,List<MarkupAttribute>,string)

Method in [BuiltInMarkupReplacer](/docs/api/csharp/yarn.markup.builtinmarkupreplacer.md)

## Summary


Produces replacement text for a marker.


```csharp
public List<LineParser.MarkupDiagnostic> ProcessReplacementMarker(MarkupAttribute marker, StringBuilder childBuilder, List<MarkupAttribute> childAttributes, string localeCode)
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
if any.

