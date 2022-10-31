# CompilationJob.CreateFromString(string,string,Library)

Method in [CompilationJob](api/csharp/yarn.compiler.compilationjob.md)

## Summary


Creates a new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  using the contents
of a string.


```csharp
public static CompilationJob CreateFromString(string fileName, string source, Library library = null)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` fileName|The name to assign to the compiled file.|
|`string` source|The text to compile.|
|[Yarn.Library](api/csharp/yarn.library.md) library|Library of function definitions to use during compilation.|

## Returns

A new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a> .

