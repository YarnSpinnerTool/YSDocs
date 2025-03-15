# CompilationJob

Struct in [Yarn.Compiler](yarn.compiler.md)

Inherits from `System.ValueType`

## Summary

An object that contains Yarn source code to compile, and instructions on how to compile it.

```csharp
public struct CompilationJob
```

## Remarks

Instances of this struct are used with [Compile(CompilationJob)](yarn.compiler.compiler.compile.md) to produce [CompilationResult](yarn.compiler.compilationresult.md) objects.

## Enums

| Name                                         | Description                                        |
| -------------------------------------------- | -------------------------------------------------- |
| [Type](yarn.compiler.compilationjob.type.md) | The type of compilation that the compiler will do. |

## Fields

| Name                                                                         | Description                                                                                      |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| [CompilationType](yarn.compiler.compilationjob.compilationtype.md)           | The type of compilation to perform.                                                              |
| [Files](yarn.compiler.compilationjob.files.md)                               | The [File](yarn.compiler.compilationjob.file.md) structs that represent the content to parse..   |
| [Library](yarn.compiler.compilationjob.library.md)                           | The [Library](yarn.compiler.compilationjob.library.md) that contains declarations for functions. |
| [VariableDeclarations](yarn.compiler.compilationjob.variabledeclarations.md) | The declarations for variables.                                                                  |

## Methods

| Name                                                                                        | Description                                                                                                  |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| [CreateFromFiles(IEnumerable,Library)](yarn.compiler.compilationjob.createfromfiles-1.md)   | Creates a new [CompilationJob](yarn.compiler.compilationjob.md) using the contents of a collection of files. |
| [CreateFromFiles(string\[\])](yarn.compiler.compilationjob.createfromfiles-2.md)            | Creates a new [CompilationJob](yarn.compiler.compilationjob.md) using the contents of a collection of files. |
| [CreateFromString(string,string,Library)](yarn.compiler.compilationjob.createfromstring.md) | Creates a new [CompilationJob](yarn.compiler.compilationjob.md) using the contents of a string.              |

## Structs

| Name                                         | Description                                   |
| -------------------------------------------- | --------------------------------------------- |
| [File](yarn.compiler.compilationjob.file.md) | Represents the contents of a file to compile. |
