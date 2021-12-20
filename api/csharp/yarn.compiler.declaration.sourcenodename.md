# SourceNodeName

Property in [Declaration](/api/csharp/yarn.compiler.declaration.md)

## Summary


Gets the name of the node in which this Declaration was found.


```csharp
public string SourceNodeName { get => sourceNodeName; internal set => sourceNodeName = value; }
```

## Remarks


If this  <a href="yarn.compiler.declaration.md">Declaration</a>  was not found in a Yarn
source file, this will be  <code>null</code> .


