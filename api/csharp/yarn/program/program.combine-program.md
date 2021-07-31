# Combine\(Program\[\]\)

Creates a new Program by merging multiple Programs together.

```csharp
public static Program Combine(params Program[] programs)
```

## Remarks

The new program will contain every node from every input program.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`Program[]`](./) programs | The Programs to combine together. |

## Return Type

[`Program`](./): The new, combined program.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Program.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Program.cs#L74), line 74.

