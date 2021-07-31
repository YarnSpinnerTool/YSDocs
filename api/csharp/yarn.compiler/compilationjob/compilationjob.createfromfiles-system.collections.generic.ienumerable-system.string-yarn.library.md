# CreateFromFiles\(IEnumerable&lt;String&gt;, Library\)

Creates a new [`CompilationJob`](./) using the contents of a collection of files.

```csharp
public static CompilationJob CreateFromFiles(IEnumerable<string> paths, Library library = null)
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`String}`](https://docs.microsoft.com/dotnet/api/System.Collections.Generic.IEnumerable{System.String}) paths | The paths to the files. |
| [`Library`](../../yarn/library/) library |  |

## Return Type

[`CompilationJob`](./): A new [`CompilationJob`](./).

## Namespace

[`Yarn.Compiler`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L499), line 499.

