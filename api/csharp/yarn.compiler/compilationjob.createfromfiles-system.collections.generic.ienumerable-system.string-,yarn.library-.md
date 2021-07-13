# CompilationJob.CreateFromFiles Method

Creates a new [`CompilationJob`](/api/csharp/yarn.compiler/compilationjob.md) using the contents
of a collection of files.


```csharp
public static CompilationJob CreateFromFiles(IEnumerable<string> paths, Library library = null)
```

## Parameters
|Parameter|Description|
|:---|:---|
|[`String}`](https://docs.microsoft.com/dotnet/api/System.Collections.Generic.IEnumerable{System.String}) paths|The paths to the files.|
|[`Library`](/api/csharp/yarn/library.md) library||
## Return Type
[`CompilationJob`](/api/csharp/yarn.compiler/compilationjob.md): A new [`CompilationJob`](/api/csharp/yarn.compiler/compilationjob.md).



## Namespace
[`Yarn.Compiler`](/api/csharp/yarn.compiler/README.md)

## Assembly
YarnSpinner.Compiler.dll

## Source
Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L499), line 499.
