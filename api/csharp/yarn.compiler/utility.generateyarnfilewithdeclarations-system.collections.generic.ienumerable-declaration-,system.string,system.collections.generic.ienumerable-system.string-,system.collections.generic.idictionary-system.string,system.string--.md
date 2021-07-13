# Utility.GenerateYarnFileWithDeclarations Method

Generates a Yarn script that contains a node that declares
variables.


```csharp
public static string GenerateYarnFileWithDeclarations(IEnumerable<Declaration> declarations, string title = "Program", IEnumerable<string> tags = null, IDictionary<string, string> headers = null)
```
## Remarks
This method is intended to be called by tools that let
the user manage variable declarations. Such tools can read the
existing variable declarations in from a script (by compiling
the script with the `DeclarationsOnly` [`CompilationType`](/api/csharp/yarn.compiler/compilationjob.compilationtype.md)), allow the user to
make changes, and then write the changes to disk by calling
this method and saving the results.

## Parameters
|Parameter|Description|
|:---|:---|
|[`Declaration}`](https://docs.microsoft.com/dotnet/api/System.Collections.Generic.IEnumerable{Yarn.Compiler.Declaration}) declarations|The collection of [`Declaration`](/api/csharp/yarn.compiler/declaration.md) objects to include in the output.|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) title|The title of the node that should be generated.|
|[`String}`](https://docs.microsoft.com/dotnet/api/System.Collections.Generic.IEnumerable{System.String}) tags|The collection of tags that should be generated for the node. If this is ``, no tags will be generated.|
|[`String}`](https://docs.microsoft.com/dotnet/api/System.Collections.Generic.IDictionary{System.String,System.String}) headers|The collection of additional headers that should be generated for the node. If this is ``, no additional headers will be generated.|
## Return Type
[`string`](https://docs.microsoft.com/dotnet/api/System.String): A string containing a Yarn script that declares the
specified variables.



<div class="class-metadata">

Parent: [`Utility`](/api/csharp/yarn.compiler/utility.md), Namespace: [`Yarn.Compiler`](/api/csharp/yarn.compiler/README.md), Assembly: YarnSpinner.Compiler.dll
</div>

## Source
Defined in [YarnSpinner.Compiler/Utility.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Utility.cs#L45), line 45.
