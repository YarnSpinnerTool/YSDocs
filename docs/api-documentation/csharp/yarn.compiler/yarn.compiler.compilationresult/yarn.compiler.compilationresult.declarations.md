# Declarations

Property in [CompilationResult](./)

## Summary

Gets the collection of variable declarations that were found during compilation.

```csharp
public IEnumerable<Declaration> Declarations { get; internal set; }
```

## Remarks

This value will be `null` if the [CompilationJob](../yarn.compiler.compilationjob/) object's [CompilationType](../yarn.compiler.compilationjob/yarn.compiler.compilationjob.compilationtype.md) value was not [DeclarationsOnly](../yarn.compiler.compilationjob/yarn.compiler.compilationjob.type/yarn.compiler.compilationjob.type.declarationsonly.md) or [FullCompilation](../yarn.compiler.compilationjob/yarn.compiler.compilationjob.type/yarn.compiler.compilationjob.type.fullcompilation.md) .
