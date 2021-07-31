# SourceNodeLine

Gets the line number at which this Declaration was found in the node indicated by [`SourceNodeName`](declaration.sourcenodename.md).

```csharp
public int SourceNodeLine { get; }
```

## Remarks

If this [`Declaration`](./) was not found in a Yarn source file, this will be -1.

## Namespace

[`Yarn.Compiler`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L294), line 294.

