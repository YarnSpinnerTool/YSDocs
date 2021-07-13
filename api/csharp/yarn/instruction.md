# Instruction Class

An instruction in a Yarn Program.


```csharp
public sealed class Instruction : IMessage<Instruction>, IMessage, IEquatable<Instruction>, IDeepCloneable<Instruction>
```



## Properties
|Name|Description|
|:---|:---|
|[`Opcode`](/api/csharp/yarn/instruction.opcode.md)| The operation that this instruction will perform. |
|[`Operands`](/api/csharp/yarn/instruction.operands.md)| The list of operands, if any, that this instruction uses. |
## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L484), line 484.
