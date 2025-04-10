# Emit(IToken?,Instruction\[])

Method in [NodeGroupCompiler](yarn.compiler.nodegroupcompiler.md)

## Summary

Adds instructions to the current node in the [Program](yarn.program.md) .

```csharp
public void Emit(IToken? startToken, params Instruction[] instructions)
```

## Remarks

Called by instances of `Yarn.Compiler.CodeGenerationVisitor` while walking the parse tree.

## Parameters

| Name                               | Description                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------- |
| `Yarn.Instruction[]` instructions  | The instructions to add.                                                                           |
| `Antlr4.Runtime.IToken` startToken | The first token in the expression or statement that was responsible for emitting this instruction. |
