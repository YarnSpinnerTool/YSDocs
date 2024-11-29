# LocalizedLine.InvalidLine

Field in [LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md)

## Summary


A  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  object that represents content not
being found.


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

