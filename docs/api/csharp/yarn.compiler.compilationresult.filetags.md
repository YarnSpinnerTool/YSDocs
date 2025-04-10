# FileTags

Property in [CompilationResult](yarn.compiler.compilationresult.md)

## Summary

Gets the collection of file-level tags found in the source code.

```csharp
public Dictionary<string, IEnumerable<string>> FileTags { get; internal set; };
```

## Remarks

The keys of this dictionary are the file names (as indicated by the [FileName](yarn.compiler.compilationjob.file.filename.md) property of the [CompilationJob](yarn.compiler.compilationjob.md) 's [Files](yarn.compiler.compilationjob.files.md) collection), and the values are the file tags associated with that file.
