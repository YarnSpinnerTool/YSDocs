# Declaration.SourceFileName

Property in [Declaration](/docs/api/csharp/yarn.compiler.declaration.md)

## Summary


Gets the name of the file in which this Declaration was found.


```csharp
public string SourceFileName { get; internal set; };
```

## Remarks


If this  <a href="yarn.compiler.declaration.md">Declaration</a>  was not found in a Yarn
source file, this will be  <a href="yarn.compiler.declaration.externaldeclaration.md">ExternalDeclaration</a> .


