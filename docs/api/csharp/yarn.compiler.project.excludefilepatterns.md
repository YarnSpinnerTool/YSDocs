# Project.ExcludeFilePatterns

Property in [Project](/docs/api/csharp/yarn.compiler.project.md)

## Summary


Gets or sets the collection of file search patterns that should be
excluded from this project.


```csharp
public IEnumerable<string> ExcludeFilePatterns { get; set; }
```

## Remarks


If a file is matched by a pattern in  <a href="yarn.compiler.project.sourcefilepatterns.md">SourceFilePatterns</a> , and is also matched by a pattern in
<a href="yarn.compiler.project.excludefilepatterns.md">ExcludeFilePatterns</a> , then it is not included in the
value returned by  <a href="yarn.compiler.project.sourcefiles.md">SourceFiles</a> .


