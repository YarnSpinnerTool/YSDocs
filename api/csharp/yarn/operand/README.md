# Operand

A value used by an Instruction.

```csharp
public sealed class Operand : IMessage<Operand>, IMessage, IEquatable<Operand>, IDeepCloneable<Operand>
```

## Properties

| Name | Description |
| :--- | :--- |
| [`BoolValue`](operand.boolvalue.md) | A boolean \(true or false\). |
| [`FloatValue`](operand.floatvalue.md) | A floating point number. |
| [`StringValue`](operand.stringvalue.md) | A string. |
| [`ValueCase`](operand.valuecase.md) |  |

## Methods

| Name | Description |
| :--- | :--- |
| [`ClearValue()`](operand.clearvalue.md) |  |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L754), line 754.

