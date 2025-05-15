# CompilationJob.CreateFromString(string,string,Library?,int)

Method in [CompilationJob](/docs/api/csharp/yarn.compiler.compilationjob.md)

## Summary


Creates a new  [CompilationJob](yarn.compiler.compilationjob.md)  using the contents of a
string.


```csharp
public static CompilationJob CreateFromString(string fileName, string source, Library? library = null, int languageVersion = Project.CurrentProjectFileVersion)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` fileName|The name to assign to the compiled file.|
|`string` source|The text to compile.|
|[Yarn.Library](/docs/api/csharp/yarn.library.md) library|Library of function definitions to use during compilation.|
|`int` languageVersion|The version of the Yarn language to use.|

## Returns

A new  [CompilationJob](yarn.compiler.compilationjob.md) .

