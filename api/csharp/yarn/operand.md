# Operand Class

A value used by an Instruction.


```csharp
public sealed class Operand : IMessage<Operand>, IMessage, IEquatable<Operand>, IDeepCloneable<Operand>
```



## Properties
|Name|Description|
|:---|:---|
|[`BoolValue`](/api/csharp/yarn/operand.boolvalue.md)| A boolean (true or false). |
|[`FloatValue`](/api/csharp/yarn/operand.floatvalue.md)| A floating point number. |
|[`StringValue`](/api/csharp/yarn/operand.stringvalue.md)| A string. |
|[`ValueCase`](/api/csharp/yarn/operand.valuecase.md)||
## Methods
|Name|Description|
|:---|:---|
|[`ClearValue()`](/api/csharp/yarn/operand.clearvalue.md)||
<div class="class-metadata">

Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L754), line 754.
