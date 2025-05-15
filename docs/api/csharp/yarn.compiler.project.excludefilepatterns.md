# Project.ExcludeFilePatterns

Property in [Project](/docs/api/csharp/yarn.compiler.project.md)

## Summary


Gets or sets the collection of file search patterns that should be
excluded from this project.


```csharp
public IEnumerable<string> ExcludeFilePatterns { get; set; };
```

## Remarks


If a file is matched by a pattern in  [SourceFilePatterns](yarn.compiler.project.sourcefilepatterns.md) , and is also matched by a pattern in
[ExcludeFilePatterns](yarn.compiler.project.excludefilepatterns.md) , then it is not included in the
value returned by  [SourceFiles](yarn.compiler.project.sourcefiles.md) .


