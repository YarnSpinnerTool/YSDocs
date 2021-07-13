# Declaration.SourceNodeLine Property

Gets the line number at which this Declaration was found in the node
indicated by [`SourceNodeName`](/api/csharp/yarn.compiler/declaration.sourcenodename.md).


```csharp
public int SourceNodeLine { get; }
```
## Remarks

If this [`Declaration`](/api/csharp/yarn.compiler/declaration.md) was not found in a Yarn
source file, this will be -1.




<div class="class-metadata">

Parent: [`Declaration`](/api/csharp/yarn.compiler/declaration.md), Namespace: [`Yarn.Compiler`](/api/csharp/yarn.compiler/README.md), Assembly: YarnSpinner.Compiler.dll
</div>

## Source
Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L294), line 294.
