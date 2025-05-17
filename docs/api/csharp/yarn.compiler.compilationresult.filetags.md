# CompilationResult.FileTags

Property in [CompilationResult](/docs/api/csharp/yarn.compiler.compilationresult.md)

## Summary


Gets the collection of file-level tags found in the source code.


```csharp
public Dictionary<string, IEnumerable<string>> FileTags { get; internal set; }
```

## Remarks

The keys of this dictionary are the file names (as
indicated by the  [FileName](yarn.compiler.compilationjob.file.filename.md)  property
of the  [Files](yarn.compiler.compilationjob.md">CompilationJob</a> 's  <a href="yarn.compiler.compilationjob.files.md)  collection), and the values are the
file tags associated with that file.


