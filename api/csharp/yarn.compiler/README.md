# Yarn.Compiler Namespace

Contains classes for compiling Yarn script into programs.

## Structs

| Name | Description |
| :--- | :--- |
| [`CompilationJob`](compilationjob/) |  |
| [`CompilationJob.File`](compilationjob.file/) | Represents the contents of a file to compile. |
| [`CompilationResult`](compilationresult/) |  |
| [`StringInfo`](stringinfo/) | Information about a string. Stored inside a string table, which is produced from the Compiler. |

## Enums

| Name | Description |
| :--- | :--- |
| [`CompilationJob.Type`](compilationjob.type/) |  |
| [`Declaration.Type`](declaration.type/) | Enumerates the different types of [`Declaration`](declaration/) structs that may be encountered. |

## Classes

| Name | Description |
| :--- | :--- |
| [`Compiler`](compiler/) | Compiles Yarn code. |
| [`CompilerException`](compilerexception/) | An exception representing something going wrong during compilation. |
| [`Declaration`](declaration/) |  |
| [`Declaration.Parameter`](declaration.parameter/) | A parameter for a function [`Declaration`](declaration/). |
| [`ParseException`](parseexception.md) | An exception representing something going wrong during parsing. |
| [`TypeException`](typeexception.md) | An exception representing something going wrong during type checking. |
| [`Utility`](utility/) | Utility methods for working with line tags. |

