# CreateFromString(string,string,Library)

Method in [CompilationJob](yarn.compiler.compilationjob.md)

## Summary

Creates a new [CompilationJob](yarn.compiler.compilationjob.md) using the contents of a string.

```csharp
public static CompilationJob CreateFromString(string fileName, string source, Library library = null)
```

## Parameters

| Name                                    | Description                                                |
| --------------------------------------- | ---------------------------------------------------------- |
| `string` fileName                       | The name to assign to the compiled file.                   |
| `string` source                         | The text to compile.                                       |
| [Yarn.Library](yarn.library.md) library | Library of function definitions to use during compilation. |

## Returns

A new [CompilationJob](yarn.compiler.compilationjob.md) .
