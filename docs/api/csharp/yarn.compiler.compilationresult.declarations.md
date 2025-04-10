# Declarations

Property in [CompilationResult](yarn.compiler.compilationresult.md)

## Summary

Gets the collection of variable declarations that were found during compilation.

```csharp
public IEnumerable<Declaration> Declarations { get; internal set; };
```

## Remarks

This value will be `null` if the [CompilationJob](yarn.compiler.compilationjob.md) object's [CompilationType](yarn.compiler.compilationjob.compilationtype.md) value was not [TypeCheck](yarn.compiler.compilationjob.type.typecheck.md) or [FullCompilation](yarn.compiler.compilationjob.type.fullcompilation.md) .
