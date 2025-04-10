# ToString(Library?,CompilationResult?)

Method in [BasicBlock](yarn.compiler.basicblock.md)

## Summary

Gets a string containing the textual description of the instructions in this [BasicBlock](yarn.compiler.basicblock.md) .

```csharp
public string ToString(Library? library, CompilationResult? compilationResult)
```

## Parameters

| Name                                                                                    | Description                                                                                                          |
| --------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Library](yarn.library.md) library                                                 | The [Library](yarn.library.md) to use when converting instructions to strings.                                       |
| [Yarn.Compiler.CompilationResult](yarn.compiler.compilationresult.md) compilationResult | The [CompilationResult](yarn.compiler.compilationresult.md) that produced [Node](yarn.compiler.basicblock.node.md) . |

## Returns

A string containing the text version of the instructions.
