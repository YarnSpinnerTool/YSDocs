# Instruction

An instruction in a Yarn Program.

```csharp
public sealed class Instruction : IMessage<Instruction>, IMessage, IEquatable<Instruction>, IDeepCloneable<Instruction>
```

## Properties

| Name | Description |
| :--- | :--- |
| [`Opcode`](instruction.opcode.md) | The operation that this instruction will perform. |
| [`Operands`](instruction.operands.md) | The list of operands, if any, that this instruction uses. |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L484), line 484.

