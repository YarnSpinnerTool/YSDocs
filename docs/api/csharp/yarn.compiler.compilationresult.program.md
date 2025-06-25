# Program

Property in [CompilationResult](yarn.compiler.compilationresult.md)

## Summary

Gets the compiled Yarn program that the [Compiler](yarn.compiler.compiler.md)\
produced.

```csharp
public Program? Program { get; internal set; }
```

## Remarks

This value will be `null` if there were errors\
in the compilation. If this is the case, [Diagnostics](yarn.compiler.compilationresult.diagnostics.md)\
will contain information describing the errors.

It will also be `null` if the [CompilationJob](yarn.compiler.compilationjob.md) object's [CompilationType](yarn.compiler.compilationjob.compilationtype.md) value was not [FullCompilation](yarn.compiler.compilationjob.type.fullcompilation.md).
