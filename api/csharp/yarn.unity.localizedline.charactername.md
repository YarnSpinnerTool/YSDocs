# CharacterName

Property in [LocalizedLine](/api/csharp/yarn.unity.localizedline.md)

## Summary


The name of the character, if present.


```csharp
public string CharacterName
        {
            get
            {
                if (Text.TryGetAttributeWithName("character", out var characterNameAttribute))
                {
                    if (characterNameAttribute.Properties.TryGetValue("name", out var value))
                    {
                        return value.StringValue;
                    }
                }
                return null;
            }
        }
```

## Remarks


This value will be  <code>null</code>  if the line does not
have a character name.


