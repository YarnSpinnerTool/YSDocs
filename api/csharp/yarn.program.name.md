# Name

Property in [Program](/api/csharp/yarn.program.md)

## Summary


The name of the program.


```csharp
[global::System.Diagnostics.DebuggerNonUserCodeAttribute]
    public string Name {
      get { return name_; }
      set {
        name_ = pb::ProtoPreconditions.CheckNotNull(value, "value");
      }
    }
```

