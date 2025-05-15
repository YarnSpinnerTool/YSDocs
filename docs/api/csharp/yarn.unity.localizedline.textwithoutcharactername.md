# LocalizedLine.TextWithoutCharacterName

Property in [LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md)

## Summary


The underlying  [MarkupParseResult](yarn.markup.markupparseresult.md)  for this
line, with any `character` attribute removed.


```csharp
public Markup.MarkupParseResult TextWithoutCharacterName
{
            get; }
```

## Remarks


If the line has no `character` attribute, this method returns the
same value as  [Text](yarn.unity.localizedline.text.md) .


