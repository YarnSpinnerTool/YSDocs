# Declaration.SourceFileName

Property in [Declaration](/docs/api/csharp/yarn.compiler.declaration.md)

## Summary


Gets the name of the file in which this Declaration was found.


```csharp
public string SourceFileName { get; internal set; }
```

## Remarks


If this  [Declaration](yarn.compiler.declaration.md)  was not found in a Yarn
source file, this will be  [ExternalDeclaration](yarn.compiler.declaration.externaldeclaration.md) .


