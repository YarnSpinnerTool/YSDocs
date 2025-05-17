# CompilationResult.Declarations

Property in [CompilationResult](/docs/api/csharp/yarn.compiler.compilationresult.md)

## Summary


Gets the collection of variable declarations that were found during
compilation.


```csharp
public IEnumerable<Declaration> Declarations { get; internal set; }
```

## Remarks


This value will be  <code>null</code>  if the  <a href="yarn.compiler.compilationjob.md">CompilationJob</a>  object's  <a href="yarn.compiler.compilationjob.compilationtype.md">CompilationType</a>  value was not  <a href="yarn.compiler.compilationjob.type.typecheck.md">TypeCheck</a>  or  <a href="yarn.compiler.compilationjob.type.fullcompilation.md">FullCompilation</a> .


