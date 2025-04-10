# InvalidLine

Field in [LocalizedLine](yarn.unity.localizedline.md)

## Summary

A [LocalizedLine](yarn.unity.localizedline.md) object that represents content not being found.

```csharp
public static readonly LocalizedLine InvalidLine = new LocalizedLine
{
    Asset = null,
    Metadata = System.Array.Empty<string>(),
    RawText = "!! ERROR: Missing line!",
    Substitutions = System.Array.Empty<string>(),
    TextID = "<missing>",
    Text = new Markup.MarkupParseResult { Text = "!! ERROR: Missing line!", Attributes = new System.Collections.Generic.List<Markup.MarkupAttribute>() }
};
```
