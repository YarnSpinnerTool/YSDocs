# CompilationJob

Struct in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.ValueType`

## Summary


An object that contains Yarn source code to compile, and instructions on
how to compile it.


```csharp
public struct CompilationJob
```

## Remarks


Instances of this struct are used with  [CompilationResult](yarn.compiler.compiler.compile.md">Compile(CompilationJob)</a>  to produce  <a href="yarn.compiler.compilationresult.md)  objects.


## Enums

|Name|Description|
|:---|:---|
|[Type](/docs/api/csharp/yarn.compiler.compilationjob.type.md)|The type of compilation that the compiler will do.|

## Fields

|Name|Description|
|:---|:---|
|[CompilationType](/docs/api/csharp/yarn.compiler.compilationjob.compilationtype.md)|The type of compilation to perform.|
|[Declarations](/docs/api/csharp/yarn.compiler.compilationjob.declarations.md)|The declarations for variables and functions.|
|[Files](/docs/api/csharp/yarn.compiler.compilationjob.files.md)|The  [File](yarn.compiler.compilationjob.file.md)  structs that represent the content to parse..|
|[Library](/docs/api/csharp/yarn.compiler.compilationjob.library.md)|The  [Library](yarn.compiler.compilationjob.library.md)  that contains declarations for functions.|

## Methods

|Name|Description|
|:---|:---|
|[CreateFromFiles(IEnumerable<string>,Library?)](/docs/api/csharp/yarn.compiler.compilationjob.createfromfiles-1.md)|Creates a new  [CompilationJob](yarn.compiler.compilationjob.md)  using the contents of a collection of files.|
|[CreateFromFiles(string[])](/docs/api/csharp/yarn.compiler.compilationjob.createfromfiles-2.md)|Creates a new  [CompilationJob](yarn.compiler.compilationjob.md)  using the contents of a collection of files.|
|[CreateFromString(string,string,Library?,int)](/docs/api/csharp/yarn.compiler.compilationjob.createfromstring.md)|Creates a new  [CompilationJob](yarn.compiler.compilationjob.md)  using the contents of a string.|

## Properties

|Name|Description|
|:---|:---|
|[CancellationToken](/docs/api/csharp/yarn.compiler.compilationjob.cancellationtoken.md)|A cancellation token that can be used to signal that the compilation should be cancelled.|
|[LanguageVersion](/docs/api/csharp/yarn.compiler.compilationjob.languageversion.md)|Gets or sets the version of the Yarn language.|
|[TypeDeclarations](/docs/api/csharp/yarn.compiler.compilationjob.typedeclarations.md)|The collection of type declarations that should be imported and made available to the compiler, prior to compilation.|
|[VariableDeclarations](/docs/api/csharp/yarn.compiler.compilationjob.variabledeclarations.md)|The declarations for variables.|

## Structs

|Name|Description|
|:---|:---|
|[File](/docs/api/csharp/yarn.compiler.compilationjob.file.md)|Represents the contents of a file to compile.|

