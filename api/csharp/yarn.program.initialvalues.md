# InitialValues

Property in [Program](/api/csharp/yarn.program.md)

## Summary


The collection of initial values for variables; if a PUSH_VARIABLE
instruction is run, and the value is not found in the storage, this
value will be used


```csharp
[global::System.Diagnostics.DebuggerNonUserCodeAttribute]
    public pbc::MapField<string, global::Yarn.Operand> InitialValues {
      get { return initialValues_; }
    }
```

