# Path

Property in [Project](yarn.compiler.project.md)

## Summary

Gets the path that the [Project](yarn.compiler.project.md) was loaded from.

```csharp
public string Path { get; set; }
```

## Remarks

This value is not stored when the file is saved, but is instead determined when the file is loaded by [LoadFromFile(string)](yarn.compiler.project.loadfromfile.md) .
