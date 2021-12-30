# CompilationJob

Struct in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.ValueType`

## Summary


An object that contains Yarn source code to compile, and instructions on
how to compile it.


```csharp
public struct CompilationJob
```

## Remarks


Instances of this struct are used with  <a href="yarn.compiler.compiler.compile.md">Compile(CompilationJob)</a>  to produce  <a href="yarn.compiler.compilationresult.md">CompilationResult</a>  objects.


## Types

|Name|Description|
|:---|:---|
|[File](/api/csharp/yarn.compiler.compilationjob.file.md)|Represents the contents of a file to compile.|
|[Type](/api/csharp/yarn.compiler.compilationjob.type.md)|The type of compilation that the compiler will do.|

## Fields

|Name|Description|
|:---|:---|
|[CompilationType](/api/csharp/yarn.compiler.compilationjob.compilationtype.md)|The type of compilation to perform.|
|[Files](/api/csharp/yarn.compiler.compilationjob.files.md)|The  <a href="yarn.compiler.compilationjob.file.md">File</a>  structs that represent the content to parse..|
|[Library](/api/csharp/yarn.compiler.compilationjob.library.md)|The  <a href="yarn.compiler.compilationjob.library.md">Library</a>  that contains declarations for functions.|
|[VariableDeclarations](/api/csharp/yarn.compiler.compilationjob.variabledeclarations.md)|The declarations for variables.|

## Methods

|Name|Description|
|:---|:---|
|[CreateFromFiles(IEnumerable<string>,Library)](/api/csharp/yarn.compiler.compilationjob.createfromfiles-1.md)|Creates a new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  using the contents of a collection of files.|
|[CreateFromFiles(string[])](/api/csharp/yarn.compiler.compilationjob.createfromfiles-2.md)|Creates a new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  using the contents of a collection of files.|
|[CreateFromString(string,string,Library)](/api/csharp/yarn.compiler.compilationjob.createfromstring.md)|Creates a new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  using the contents of a string.|

