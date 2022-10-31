# CompilationJob.CreateFromFiles(IEnumerable<string>,Library)

Method in [CompilationJob](api/csharp/yarn.compiler.compilationjob.md)

## Summary


Creates a new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  using the contents of a
collection of files.


```csharp
public static CompilationJob CreateFromFiles(IEnumerable<string> paths, Library library = null)
```

## Parameters

|Name|Description|
|:---|:---|
|`System.Collections.Generic.IEnumerable<string>` paths|The paths to the files.|
|[Yarn.Library](api/csharp/yarn.library.md) library|The  <a href="yarn.compiler.compilationjob.library.md">Library</a>  containing functions to use for this compilation.|

## Returns

A new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a> .

