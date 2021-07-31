# Parameters

Gets the [`Declaration.Parameter`](../declaration.parameter/)s associated with this [`Declaration`](./).

```csharp
public Declaration.Parameter[] Parameters { get; }
```

## Remarks

For declarations whose [`DeclarationType`](declaration.declarationtype.md) is [`Variable`](../declaration.type/declaration.type.variable.md), this array will be empty.

## Namespace

[`Yarn.Compiler`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L257), line 257.

