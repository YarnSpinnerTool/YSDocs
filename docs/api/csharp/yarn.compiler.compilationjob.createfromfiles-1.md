# CreateFromFiles(IEnumerable\<string>,Library)

Method in [CompilationJob](yarn.compiler.compilationjob.md)

## Summary

Creates a new [CompilationJob](yarn.compiler.compilationjob.md) using the contents of a collection of files.

```csharp
public static CompilationJob CreateFromFiles(IEnumerable<string> paths, Library library = null)
```

## Parameters

| Name                                                   | Description                                                                                              |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| `System.Collections.Generic.IEnumerable<string>` paths | The paths to the files.                                                                                  |
| [Yarn.Library](yarn.library.md) library                | The [Library](yarn.compiler.compilationjob.library.md) containing functions to use for this compilation. |

## Returns

A new [CompilationJob](yarn.compiler.compilationjob.md) .
