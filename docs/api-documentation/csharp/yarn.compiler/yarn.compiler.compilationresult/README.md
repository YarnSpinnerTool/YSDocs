# CompilationResult

Struct in [Yarn.Compiler](../)

Inherits from `System.ValueType`

## Summary

The result of a compilation.

```csharp
public struct CompilationResult
```

## Remarks

Instances of this struct are produced as a result of supplying a [CompilationJob](../yarn.compiler.compilationjob/) to [Compile(CompilationJob)](../yarn.compiler.compiler/yarn.compiler.compiler.compile.md) .

## Properties

| Name                                                                                        | Description                                                                                                                                                       |
| ------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ContainsImplicitStringTags](yarn.compiler.compilationresult.containsimplicitstringtags.md) | Gets a value indicating whether the compiler had to create line IDs for lines in the source code that lacked `#line:` tags.                                       |
| [DebugInfo](yarn.compiler.compilationresult.debuginfo.md)                                   | Gets the collection of [DebugInfo](yarn.compiler.compilationresult.debuginfo.md) objects for each node in [Program](yarn.compiler.compilationresult.program.md) . |
| [Declarations](yarn.compiler.compilationresult.declarations.md)                             | Gets the collection of variable declarations that were found during compilation.                                                                                  |
| [Diagnostics](yarn.compiler.compilationresult.diagnostics.md)                               | Gets the collection of [Diagnostic](../yarn.compiler.diagnostic/) objects that describe problems in the source code.                                              |
| [FileTags](yarn.compiler.compilationresult.filetags.md)                                     | Gets the collection of file-level tags found in the source code.                                                                                                  |
| [Program](yarn.compiler.compilationresult.program.md)                                       | Gets the compiled Yarn program that the [Compiler](../yarn.compiler.compiler/) produced.                                                                          |
| [StringTable](yarn.compiler.compilationresult.stringtable.md)                               | Gets a dictionary mapping line IDs to StringInfo objects.                                                                                                         |
