# LocaleCode

Property in [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md)

## Summary

Gets the user's current locale identifier, as a BCP-47 code.

```csharp
public abstract string LocaleCode { get; set; }
```

## Remarks

This value is used to control how certain replacement markers behave (for example, the `[plural]` marker, which behaves differently depending on the user's locale.)
