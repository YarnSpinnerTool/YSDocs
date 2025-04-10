# SourceFiles

Property in [Project](yarn.compiler.project.md)

## Summary

Gets the collection of Yarn files that should be used to compile the project.

```csharp
public IEnumerable<string> SourceFiles
{
            get; }
```

## Remarks

This collection uses a `Yarn.Compiler.Project.Matcher` to find all files specified by [SourceFilePatterns](yarn.compiler.project.sourcefilepatterns.md) , excluding those that are specified by [ExcludeFilePatterns](yarn.compiler.project.excludefilepatterns.md) .
