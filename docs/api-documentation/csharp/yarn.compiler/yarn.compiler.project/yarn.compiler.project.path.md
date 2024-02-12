# Path

Property in [Project](./)

## Summary

Gets the path that the [Project](./) was loaded from.

```csharp
public string Path { get; set; }
```

## Remarks

This value is not stored when the file is saved, but is instead determined when the file is loaded by [LoadFromFile(string)](yarn.compiler.project.loadfromfile.md) .
