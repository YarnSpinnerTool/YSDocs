# Diagnostics

Property in [CompilationResult](yarn.compiler.compilationresult.md)

## Summary

Gets the collection of [Diagnostic](yarn.compiler.diagnostic.md) objects that\
describe problems in the source code.

```csharp
public IEnumerable<Diagnostic> Diagnostics { get; internal set; }
```

## Remarks

If the compiler encounters errors while compiling source code, the[CompilationResult](yarn.compiler.compilationresult.md) it produces will have a [Program](yarn.compiler.compilationresult.program.md) value of `null` . To help figure out\
what the error is, users should consult the contents of this\
property.
