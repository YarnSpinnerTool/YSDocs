# isImplicitTag

Field in [StringInfo](yarn.compiler.stringinfo.md)

## Summary

Indicates whether this string's line ID was implicitly generated.

```csharp
public bool isImplicitTag;
```

## Remarks

Implicitly generated line IDs are not guaranteed to remain the same across multiple compilations. To ensure that a line ID remains the same, you must define it by adding a line tag to the line.
