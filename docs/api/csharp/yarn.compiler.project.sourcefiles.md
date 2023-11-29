# Project.SourceFiles

Property in [Project](/docs/api/csharp/yarn.compiler.project.md)

## Summary


Gets the collection of Yarn files that should be used to compile the
project.


```csharp
public IEnumerable<string> SourceFiles
{
            get; }
```

## Remarks


This collection uses a  <code>Yarn.Compiler.Project.Matcher</code>  to find all files
specified by  <a href="yarn.compiler.project.sourcefilepatterns.md">SourceFilePatterns</a> , excluding those that
are specified by  <a href="yarn.compiler.project.excludefilepatterns.md">ExcludeFilePatterns</a> .


