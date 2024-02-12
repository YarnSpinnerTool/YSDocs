# CreateFromString(string,string,Library)

Method in [CompilationJob](./)

## Summary

Creates a new [CompilationJob](./) using the contents of a string.

```csharp
public static CompilationJob CreateFromString(string fileName, string source, Library library = null)
```

## Parameters

| Name                                             | Description                                                |
| ------------------------------------------------ | ---------------------------------------------------------- |
| `string` fileName                                | The name to assign to the compiled file.                   |
| `string` source                                  | The text to compile.                                       |
| [Yarn.Library](../../yarn/yarn.library/) library | Library of function definitions to use during compilation. |

## Returns

A new [CompilationJob](./) .
