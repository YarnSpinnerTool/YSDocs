# Library

Property in [Dialogue](./)

## Summary

Gets the [Library](../yarn.library/) that this Dialogue uses to locate functions.

```csharp
public Library Library { get; internal set; }
```

## Remarks

When the Dialogue is constructed, the Library is initialized with the built-in operators like `+` , `-` , and so on.
