# CompilationResult.Program

Property in [CompilationResult](/docs/api/csharp/yarn.compiler.compilationresult.md)

## Summary


Gets the compiled Yarn program that the  [Compiler](yarn.compiler.compiler.md) 
produced.


```csharp
public Program? Program { get; internal set; }
```

## Remarks

<p>This value will be `null` if there were errors
in the compilation. If this is the case, [Diagnostics](yarn.compiler.compilationresult.diagnostics.md)
will contain information describing the errors.</p> <p>
It will also be `null` if the [FullCompilation](yarn.compiler.compilationjob.md">CompilationJob</a> object's <a href="yarn.compiler.compilationjob.compilationtype.md">CompilationType</a> value was not <a href="yarn.compiler.compilationjob.type.fullcompilation.md).
</p>

