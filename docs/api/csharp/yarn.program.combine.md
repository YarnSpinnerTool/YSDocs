# Program.Combine(Program[])

Method in [Program](/docs/api/csharp/yarn.program.md)

## Summary


Creates a new Program by merging multiple Programs together.


```csharp
public static Program Combine(params Program[] programs)
```

## Remarks


The new program will contain every node from every input
program.


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Program\[\]](/docs/api/csharp/yarn.program.md) programs|The Programs to combine together.|

## Returns

The new, combined program.

