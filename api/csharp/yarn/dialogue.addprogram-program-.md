# Dialogue.AddProgram Method

Loads the nodes from the specified [`Program`](/api/csharp/yarn/program.md),
and adds them to the nodes already loaded.


```csharp
public void AddProgram(Program program)
```
## Remarks

If `Yarn.Dialogue.Program` is `null`, this method has the effect
as calling [`SetProgram(Program)`](/api/csharp/yarn/dialogue.setprogram-program-.md).


## Parameters
|Parameter|Description|
|:---|:---|
|[`Program`](/api/csharp/yarn/program.md) program|The additional program to load.|


<div class="class-metadata">

Parent: [`Dialogue`](/api/csharp/yarn/dialogue.md), Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L582), line 582.
