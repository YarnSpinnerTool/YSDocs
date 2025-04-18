# Emit(IToken?,Instruction)

Method in [NodeGroupCompiler](yarn.compiler.nodegroupcompiler.md)

## Summary

Creates a new instruction, and appends it to the current node in the [Program](yarn.program.md) .

```csharp
public void Emit(IToken? startToken, Instruction instruction)
```

## Remarks

Called by instances of `Yarn.Compiler.CodeGenerationVisitor` while walking the parse tree.

## Parameters

| Name                               | Description                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------- |
| `Yarn.Instruction` instruction     | The instruction to add.                                                                            |
| `Antlr4.Runtime.IToken` startToken | The first token in the expression or statement that was responsible for emitting this instruction. |
