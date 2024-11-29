# VariableKind

Enum in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.Enum`

## Summary


Represents different kinds of variables that can be fetched from a  <a href="yarn.dialogue.md">Dialogue</a>  using  <a href="yarn.ivariableaccess.trygetvalue.md">TryGetValue(string,T)</a> .


```csharp
public enum VariableKind
{
    Unknown,
    Stored,
    Smart
}
```

## Members

|Name|Description|
|:---|:---|
|[Smart](/docs/api/csharp/yarn.variablekind.smart.md)|The variable's value is computed at run-time, and is not persisted to disk.|
|[Stored](/docs/api/csharp/yarn.variablekind.stored.md)|The variable's value is stored in memory, and may be persisted to disk.|
|[Unknown](/docs/api/csharp/yarn.variablekind.unknown.md)|The kind of the variable cannot be determined. It may not be known to the system.|

