# CompilationResult.Diagnostics

Property in [CompilationResult](/docs/api/csharp/yarn.compiler.compilationresult.md)

## Summary


Gets the collection of  [Diagnostic](yarn.compiler.diagnostic.md)  objects that
describe problems in the source code.


```csharp
public IEnumerable<Diagnostic> Diagnostics { get; internal set; }
```

## Remarks


If the compiler encounters errors while compiling source code, the
[Program](yarn.compiler.compilationresult.md">CompilationResult</a>  it produces will have a  <a href="yarn.compiler.compilationresult.program.md)  value of  `null` . To help figure out
what the error is, users should consult the contents of this
property.


