# TextWithoutCharacterName

Property in [LocalizedLine](./)

## Summary

The underlying [MarkupParseResult](../../yarn.markup/yarn.markup.markupparseresult/) for this line, with any `character` attribute removed.

```csharp
public Markup.MarkupParseResult TextWithoutCharacterName
{
            get; }
```

## Remarks

If the line has no `character` attribute, this method returns the same value as [Text](yarn.unity.localizedline.text.md) .
