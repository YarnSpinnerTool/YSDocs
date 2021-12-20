# TextWithoutCharacterName

Property in [LocalizedLine](/api/csharp/yarn.unity.localizedline.md)

## Summary


The underlying  <code>Yarn.Markup.MarkupParseResult</code>  for
this line, with any `character` attribute removed.


```csharp
public Markup.MarkupParseResult TextWithoutCharacterName
        {
            get
            {
                // If a 'character' attribute is present, remove its text
                if (Text.TryGetAttributeWithName("character", out var characterNameAttribute))
                {
                    return Text.DeleteRange(characterNameAttribute);
                }
                else
                {
                    return Text;
                }
            }
        }
```

## Remarks


If the line has no `character` attribute, this method returns
the same value as  <a href="yarn.unity.localizedline.text.md">Text</a> .


