# CompilationJob.CreateFromInputs(IEnumerable<ISourceInput>,Library?,int)

Method in [CompilationJob](/docs/api/csharp/yarn.compiler.compilationjob.md)

## Summary


Creates a new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  using the contents of a
collection of source inputs.


```csharp
public static CompilationJob CreateFromInputs(IEnumerable<ISourceInput> inputs, Library? library = null, int languageVersion = Project.CurrentProjectFileVersion)
```

## Parameters

|Name|Description|
|:---|:---|
|`System.Collections.Generic.IEnumerable<Yarn.Compiler.ISourceInput>` inputs|The inputs to the compilation.|
|[Yarn.Library](/docs/api/csharp/yarn.library.md) library|The  <a href="yarn.compiler.compilationjob.library.md">Library</a>  containing functions to use for this compilation.|
|`int` languageVersion||

## Returns

A new  <a href="yarn.compiler.compilationjob.md">CompilationJob</a> .

