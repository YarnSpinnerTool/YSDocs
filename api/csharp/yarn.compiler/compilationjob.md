# CompilationJob Struct


```csharp
public struct CompilationJob
```



## Fields
|Name|Description|
|:---|:---|
|[`CompilationType`](/api/csharp/yarn.compiler/compilationjob.compilationtype.md)| The type of compilation to perform. |
|[`Files`](/api/csharp/yarn.compiler/compilationjob.files.md)| The [`CompilationJob.File`](/api/csharp/yarn.compiler/compilationjob.file.md) structs that represent the content to parse.. |
|[`Library`](/api/csharp/yarn.compiler/compilationjob.library.md)| The [`Library`](/api/csharp/yarn.compiler/compilationjob.library.md) that contains declarations for functions. |
|[`VariableDeclarations`](/api/csharp/yarn.compiler/compilationjob.variabledeclarations.md)| The declarations for variables. |
## Methods
|Name|Description|
|:---|:---|
|[`CreateFromFiles(IEnumerable<String>, Library)`](/api/csharp/yarn.compiler/compilationjob.createfromfiles-system.collections.generic.ienumerable-system.string-,yarn.library-.md)| Creates a new [`CompilationJob`](/api/csharp/yarn.compiler/compilationjob.md) using the contents of a collection of files. |
|[`CreateFromFiles(String[])`](/api/csharp/yarn.compiler/compilationjob.createfromfiles-system.string---.md)||
|[`CreateFromString(String, String, Library)`](/api/csharp/yarn.compiler/compilationjob.createfromstring-system.string,system.string,yarn.library-.md)| Creates a new [`CompilationJob`](/api/csharp/yarn.compiler/compilationjob.md) using the contents of a string. |
<div class="class-metadata">

Namespace: [`Yarn.Compiler`](/api/csharp/yarn.compiler/README.md), Assembly: YarnSpinner.Compiler.dll
</div>

## Source
Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L442), line 442.
