# SourceTextStringID

Property in [Node](/api/csharp/yarn.node.md)

## Summary


the entry in the program's string table that contains the original
text of this node; null if this is not available    


```csharp
[global::System.Diagnostics.DebuggerNonUserCodeAttribute]
    public string SourceTextStringID {
      get { return sourceTextStringID_; }
      set {
        sourceTextStringID_ = pb::ProtoPreconditions.CheckNotNull(value, "value");
      }
    }
```

