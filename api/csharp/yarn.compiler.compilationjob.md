# CompilationJob

Struct in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.ValueType`

## Summary



```csharp
public struct CompilationJob
    {
    }
```

## Types

|Name|Description|
|:---|:---|
|[File](/api/csharp/yarn.compiler.compilationjob.file.md)|Represents the contents of a file to compile.|
|[Type](/api/csharp/yarn.compiler.compilationjob.type.md)||

## Fields

|Name|Description|
|:---|:---|
|[Files](/api/csharp/yarn.compiler.compilationjob.files.md)|The  <a href="yarn.compiler.compilationjob.file.md">File</a>  structs that represent the content to parse..|
|[Library](/api/csharp/yarn.compiler.compilationjob.library.md)|The  <a href="yarn.compiler.compilationjob.library.md">Library</a>  that contains declarations for functions.|
|[CompilationType](/api/csharp/yarn.compiler.compilationjob.compilationtype.md)|The type of compilation to perform.|
|[VariableDeclarations](/api/csharp/yarn.compiler.compilationjob.variabledeclarations.md)|The declarations for variables.|

## Methods

|Name|Description|
|:---|:---|
|[CreateFromFiles(IEnumerable<string>,Library)](/api/csharp/yarn.compiler.compilationjob.createfromfiles-1.md)|Creates a new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  using the contents of a collection of files.|
|[CreateFromFiles(string[])](/api/csharp/yarn.compiler.compilationjob.createfromfiles-2.md)||
|[CreateFromString(string,string,Library)](/api/csharp/yarn.compiler.compilationjob.createfromstring.md)|Creates a new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  using the contents of a string.|

