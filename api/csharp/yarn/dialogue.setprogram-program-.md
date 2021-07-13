# Dialogue.SetProgram Method

Loads all nodes from the provided [`Program`](/api/csharp/yarn/program.md).


```csharp
public void SetProgram(Program program)
```
## Remarks

This method replaces any existing nodes have been loaded. If
you want to load nodes from an _additional_ Program, use the
[`AddProgram(Program)`](/api/csharp/yarn/dialogue.addprogram-program-.md) method.


## Parameters
|Parameter|Description|
|:---|:---|
|[`Program`](/api/csharp/yarn/program.md) program|The [`Program`](/api/csharp/yarn/program.md) to use.|


<div class="class-metadata">

Parent: [`Dialogue`](/api/csharp/yarn/dialogue.md), Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L568), line 568.
