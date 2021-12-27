# Declaration.SourceNodeLine

Property in [Declaration](/api/csharp/yarn.compiler.declaration.md)

## Summary


Gets the line number at which this Declaration was found in the node
indicated by  <a href="yarn.compiler.declaration.sourcenodename.md">SourceNodeName</a> .


```csharp
public int SourceNodeLine { get; internal set; }
```

## Remarks


If this  <a href="yarn.compiler.declaration.md">Declaration</a>  was not found in a Yarn
source file, this will be -1.


