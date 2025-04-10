# Destination

Class in [BasicBlock](yarn.compiler.basicblock.md)

Inherits from `System.Object`

## Summary

A destination represents a [BasicBlock](yarn.compiler.basicblock.md) or node that may be run, following the execution of a [BasicBlock](yarn.compiler.basicblock.md) .

```csharp
public abstract class Destination
```

## Remarks

Destination objects represent links between blocks, or between blocks and nodes.

## Methods

| Name                                                           | Description |
| -------------------------------------------------------------- | ----------- |
| [ToString()](yarn.compiler.basicblock.destination.tostring.md) |             |

## Properties

| Name                                                           | Description                                                                                                                                                                                                                                                  |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Condition](yarn.compiler.basicblock.destination.condition.md) | The condition that causes this destination to be reached.                                                                                                                                                                                                    |
| [ReturnTo](yarn.compiler.basicblock.destination.returnto.md)   | When this destination is taken, if this value is non-null, a VM should push this block onto the call stack. When a Return instruction is reached, pop a block off the call stack and return to it. If the value is null, the VM should clear the call stack. |
