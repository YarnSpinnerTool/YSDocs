# GetLocalization(string)

Method in [YarnProject](yarn.unity.yarnproject.md)

## Summary

Gets a Localization given a locale code.

```csharp
public Localization GetLocalization(string localeCode)
```

## Parameters

| Name                | Description                                                               |
| ------------------- | ------------------------------------------------------------------------- |
| `string` localeCode | The locale code to find a [Localization](yarn.unity.localization.md) for. |

## Returns

The Localization if one is found for the locale `localeCode` ; [baseLocalization](yarn.unity.yarnproject.baselocalization.md)\
otherwise.
