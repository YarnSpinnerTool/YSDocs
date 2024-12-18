# Project.Path

Property in [Project](/docs/api/csharp/yarn.compiler.project.md)

## Summary


Gets the path that the  <a href="yarn.compiler.project.md">Project</a>  was loaded from.


```csharp
public string? Path { get; set; }
```

## Remarks


This value is not stored when the file is saved, but is instead
determined when the file is loaded by  <code>LoadFromFile(string)</code> , or provided when the  <a href="yarn.compiler.project.md">Project</a>  is constructed.


