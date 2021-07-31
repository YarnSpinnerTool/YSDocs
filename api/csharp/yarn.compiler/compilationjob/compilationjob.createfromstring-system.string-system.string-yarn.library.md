# CreateFromString\(String, String, Library\)

Creates a new [`CompilationJob`](./) using the contents of a string.

```csharp
public static CompilationJob CreateFromString(string fileName, string source, Library library = null)
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) fileName | The name to assign to the compiled file. |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) source | The text to compile. |
| [`Library`](../../yarn/library/) library |  |

## Return Type

[`CompilationJob`](./): A new [`CompilationJob`](./).

## Namespace

[`Yarn.Compiler`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L533), line 533.

