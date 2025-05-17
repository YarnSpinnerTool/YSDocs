# CompilationResult.Program

Property in [CompilationResult](/docs/api/csharp/yarn.compiler.compilationresult.md)

## Summary


Gets the compiled Yarn program that the  <a href="yarn.compiler.compiler.md">Compiler</a> 
produced.


```csharp
public Program? Program { get; internal set; }
```

## Remarks

<p>This value will be <code>null</code> if there were errors
in the compilation. If this is the case, <a href="yarn.compiler.compilationresult.diagnostics.md">Diagnostics</a>
will contain information describing the errors.</p> <p>
It will also be <code>null</code> if the <a href="yarn.compiler.compilationjob.md">CompilationJob</a> object's <a href="yarn.compiler.compilationjob.compilationtype.md">CompilationType</a> value was not <a href="yarn.compiler.compilationjob.type.fullcompilation.md">FullCompilation</a>.
</p>

