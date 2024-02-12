# AddLocalizedString(string,string)

Method in [Localization](./)

## Summary

Adds a new string to the runtime string table.

```csharp
public void AddLocalizedString(string key, string value)
```

## Remarks

This method updates the localisation's runtime string table, which is useful for adding or changing the localisation during gameplay or in a built player. It doesn't modify the asset on disk, and any changes made will be lost when gameplay ends.

## Parameters

| Name           | Description                                                                                                              |
| -------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `string` key   | The key for this string (generally, the line ID.)                                                                        |
| `string` value | The user-facing text for this string, in the language specified by [LocaleCode](yarn.unity.localization.localecode.md) . |
