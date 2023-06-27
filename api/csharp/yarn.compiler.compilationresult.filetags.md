# CompilationResult.FileTags

Property in [CompilationResult](/api/csharp/yarn.compiler.compilationresult.md)

## Summary


Gets the collection of file-level tags found in the source code.


```csharp
public Dictionary<string, IEnumerable<string>> FileTags { get; internal set; }
```

## Remarks

The keys of this dictionary are the file names (as
indicated by the  <a href="yarn.compiler.compilationjob.file.filename.md">FileName</a>  property
of the  <a href="yarn.compiler.compilationjob.md">CompilationJob</a> 's  <a href="yarn.compiler.compilationjob.files.md">Files</a>  collection), and the values are the
file tags associated with that file.


