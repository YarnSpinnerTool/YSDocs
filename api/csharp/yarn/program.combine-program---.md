# Program.Combine Method

Creates a new Program by merging multiple Programs together.


```csharp
public static Program Combine(params Program[] programs)
```
## Remarks

The new program will contain every node from every input
program.


## Parameters
|Parameter|Description|
|:---|:---|
|[`Program[]`](/api/csharp/yarn/program.md) programs|The Programs to combine together.|
## Return Type
[`Program`](/api/csharp/yarn/program.md): The new, combined program.



<div class="class-metadata">

Parent: [`Program`](/api/csharp/yarn/program.md), Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/Program.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Program.cs#L74), line 74.
