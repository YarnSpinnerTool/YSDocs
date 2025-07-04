# ProcessReplacementMarker(MarkupAttribute,StringBuilder,List\<MarkupAttribute>,string)

Method in [BuiltInMarkupReplacer](yarn.markup.builtinmarkupreplacer.md)

## Summary

Produces replacement text for a marker.

```csharp
public List<LineParser.MarkupDiagnostic> ProcessReplacementMarker(MarkupAttribute marker, StringBuilder childBuilder, List<MarkupAttribute> childAttributes, string localeCode)
```

## Parameters

| Name                                                                           | Description                                                                                                                                                               |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Markup.MarkupAttribute](yarn.markup.markupattribute.md) marker           | The marker to process into replacement text.                                                                                                                              |
| `System.Text.StringBuilder` childBuilder                                       | A `System.Text.StringBuilder` that contains the child text contained within `marker` . Use the methods on this stringbuilder to produce any text needed from this marker. |
| `System.Collections.Generic.List<Yarn.Markup.MarkupAttribute>` childAttributes | The child attributes of `marker` .                                                                                                                                        |
| `string` localeCode                                                            | A BCP-47 locale code that represents the locale in which any processing should take place.                                                                                |

## Returns

The collection of diagnostics produced during processing,\
if any.
