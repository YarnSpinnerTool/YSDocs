# CompilationResult

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


The result of a compilation.


```csharp
public class CompilationResult : ICodeDumpHelper
```

## Remarks


Instances of this class are produced as a result of supplying a  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  to  <a href="yarn.compiler.compiler.compile.md">Compile(CompilationJob)</a> .


## Methods

|Name|Description|
|:---|:---|
|[GetDescriptionForVariable(string)](/docs/api/csharp/yarn.compiler.compilationresult.getdescriptionforvariable.md)||
|[GetLabelsForNode(string)](/docs/api/csharp/yarn.compiler.compilationresult.getlabelsfornode.md)||
|[GetStringForKey(string)](/docs/api/csharp/yarn.compiler.compilationresult.getstringforkey.md)||

## Properties

|Name|Description|
|:---|:---|
|[ContainsErrors](/docs/api/csharp/yarn.compiler.compilationresult.containserrors.md)|Gets a value indicating whether this compilation result contains any error diagnostics.|
|[ContainsImplicitStringTags](/docs/api/csharp/yarn.compiler.compilationresult.containsimplicitstringtags.md)|Gets a value indicating whether the compiler had to create line IDs for lines in the source code that lacked  <code>#line:</code>  tags.|
|[DebugInfo](/docs/api/csharp/yarn.compiler.compilationresult.debuginfo.md)|Gets the collection of  <a href="yarn.compiler.compilationresult.debuginfo.md">DebugInfo</a>  objects for each node in  <a href="yarn.compiler.compilationresult.program.md">Program</a> .|
|[Declarations](/docs/api/csharp/yarn.compiler.compilationresult.declarations.md)|Gets the collection of variable declarations that were found during compilation.|
|[Diagnostics](/docs/api/csharp/yarn.compiler.compilationresult.diagnostics.md)|Gets the collection of  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  objects that describe problems in the source code.|
|[FileTags](/docs/api/csharp/yarn.compiler.compilationresult.filetags.md)|Gets the collection of file-level tags found in the source code.|
|[Program](/docs/api/csharp/yarn.compiler.compilationresult.program.md)|Gets the compiled Yarn program that the  <a href="yarn.compiler.compiler.md">Compiler</a>  produced.|
|[ProjectDebugInfo](/docs/api/csharp/yarn.compiler.compilationresult.projectdebuginfo.md)|Gets the debugging information for this compiled project.|
|[StringTable](/docs/api/csharp/yarn.compiler.compilationresult.stringtable.md)|Gets a dictionary mapping line IDs to StringInfo objects.|
|[UserDefinedTypes](/docs/api/csharp/yarn.compiler.compilationresult.userdefinedtypes.md)|Gets a collection of any types that were defined by the user in the input (for example, user-defined enum types.)|

