# LocaleCode

Property in [LineProviderBehaviour](./)

## Summary

Gets the user's current locale identifier, as a BCP-47 code.

```csharp
public abstract string LocaleCode { get; }
```

## Remarks

This value is used by the [DialogueRunner](../yarn.unity.dialoguerunner/) to control how certain replacement markers behave (for example, the `[plural]` marker, which behaves differently depending on the user's locale.)
