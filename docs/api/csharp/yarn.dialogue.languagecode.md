# LanguageCode

Property in [Dialogue](yarn.dialogue.md)

## Summary

Gets or sets the [Dialogue](yarn.dialogue.md) 's locale, as an IETF BCP 47 code.

```csharp
public string LanguageCode { get; set; }
```

## Remarks

This code is used to determine how the `plural` and `ordinal` markers determine the plural class of numbers.

For example, the code "en-US" represents the English language as used in the United States.
