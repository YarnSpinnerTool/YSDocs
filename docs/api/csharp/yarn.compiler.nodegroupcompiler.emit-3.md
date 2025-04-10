# Emit(Instruction)

Method in [NodeGroupCompiler](yarn.compiler.nodegroupcompiler.md)

## Summary

Creates a new instruction, and appends it to the current node in the [Program](yarn.program.md) . Differs from the other Emit call by not requiring a start token. This enables its use in pure synthesised elements of the Yarn.

```csharp
public void Emit(Instruction instruction)
```

## Remarks

Called by instances of `Yarn.Compiler.CodeGenerationVisitor` while walking the parse tree.

## Parameters

| Name                           | Description             |
| ------------------------------ | ----------------------- |
| `Yarn.Instruction` instruction | The instruction to add. |
