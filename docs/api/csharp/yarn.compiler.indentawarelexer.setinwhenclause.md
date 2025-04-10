# SetInWhenClause(bool)

Method in [IndentAwareLexer](yarn.compiler.indentawarelexer.md)

## Summary

Sets a value indicating whether the lexer is currently lexing an expression that's part of a 'when' clause.

```csharp
public virtual void SetInWhenClause(bool val);
```

## Remarks

This value can be accessed by calling [IsInWhenClause()](yarn.compiler.indentawarelexer.isinwhenclause.md) .

## Parameters

| Name       | Description       |
| ---------- | ----------------- |
| `bool` val | The value to set. |
