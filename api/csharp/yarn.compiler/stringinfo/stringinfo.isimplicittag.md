# isImplicitTag

Indicates whether this string's line ID was implicitly generated.

```csharp
public bool isImplicitTag
```

## Remarks

Implicitly generated line IDs are not guaranteed to remain the same across multiple compilations. To ensure that a line ID remains the same, you must define it by adding a \[line tag\]\(\) to the line.

## Namespace

[`Yarn.Compiler`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L125), line 125.

