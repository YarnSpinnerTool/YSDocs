# InitialValues

Property in [Program](yarn.program.md)

## Summary

The collection of initial values for variables; if a PUSH\_VARIABLE\
instruction is run, and the value is not found in the storage, this\
value will be used

```csharp
public pbc::MapField<string, global::Yarn.Operand> InitialValues { get; }
```
