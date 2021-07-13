# StringInfo.isImplicitTag Field

Indicates whether this string's line ID was implicitly
generated.


```csharp
public bool isImplicitTag
```
## Remarks

Implicitly generated line IDs are not guaranteed to remain the
same across multiple compilations. To ensure that a line ID
remains the same, you must define it by adding a [line
tag]({{<ref "/docs/unity/localisation.md">}}) to the line.




<div class="class-metadata">

Parent: [`StringInfo`](/api/csharp/yarn.compiler/stringinfo.md), Namespace: [`Yarn.Compiler`](/api/csharp/yarn.compiler/README.md), Assembly: YarnSpinner.Compiler.dll
</div>

## Source
Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L125), line 125.
