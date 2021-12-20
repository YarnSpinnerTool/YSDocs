# Diagnostics

Property in [UpgradeResult](/api/csharp/yarn.compiler.upgrader.upgraderesult.md)

## Summary


Gets a collection containing all  <a href="yarn.compiler.diagnostic.md">Diagnostic</a> 
objects across all of the files in  <a href="yarn.compiler.upgrader.upgraderesult.files.md">Files</a> .


```csharp
public IEnumerable<Diagnostic> Diagnostics => Files.SelectMany(f => f.Diagnostics);
```

