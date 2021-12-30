# CompilationResult

Struct in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.ValueType`

## Summary


The result of a compilation.


```csharp
public struct CompilationResult
```

## Remarks


Instances of this struct are produced as a result of supplying a  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  to  <a href="yarn.compiler.compiler.compile.md">Compile(CompilationJob)</a> .


## Properties

|Name|Description|
|:---|:---|
|[ContainsImplicitStringTags](/api/csharp/yarn.compiler.compilationresult.containsimplicitstringtags.md)|Gets a value indicating whether the compiler had to create line IDs for lines in the source code that lacked  <code>#line:</code>  tags.|
|[Declarations](/api/csharp/yarn.compiler.compilationresult.declarations.md)||
|[Diagnostics](/api/csharp/yarn.compiler.compilationresult.diagnostics.md)|Gets the collection of  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  objects that describe problems in the source code.|
|[FileTags](/api/csharp/yarn.compiler.compilationresult.filetags.md)||
|[Program](/api/csharp/yarn.compiler.compilationresult.program.md)|Gets the compiled Yarn program that the  <a href="yarn.compiler.compiler.md">Compiler</a>  produced.|
|[StringTable](/api/csharp/yarn.compiler.compilationresult.stringtable.md)|Gets a dictionary mapping line IDs to StringInfo objects.|

