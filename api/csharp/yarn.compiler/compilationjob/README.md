# CompilationJob

```csharp
public struct CompilationJob
```

## Fields

| Name | Description |
| :--- | :--- |
| [`CompilationType`](compilationjob.compilationtype.md) | The type of compilation to perform. |
| [`Files`](compilationjob.files.md) | The [`CompilationJob.File`](../compilationjob.file/) structs that represent the content to parse.. |
| [`Library`](compilationjob.library.md) | The [`Library`](compilationjob.library.md) that contains declarations for functions. |
| [`VariableDeclarations`](compilationjob.variabledeclarations.md) | The declarations for variables. |

## Methods

| Name | Description |
| :--- | :--- |
| [`CreateFromFiles(IEnumerable<String>, Library)`](compilationjob.createfromfiles-system.collections.generic.ienumerable-system.string-yarn.library.md) | Creates a new [`CompilationJob`](./) using the contents of a collection of files. |
| [`CreateFromFiles(String[])`](compilationjob.createfromfiles-system.string.md) |  |
| [`CreateFromString(String, String, Library)`](compilationjob.createfromstring-system.string-system.string-yarn.library.md) | Creates a new [`CompilationJob`](./) using the contents of a string. |

## Namespace

[`Yarn.Compiler`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L442), line 442.

