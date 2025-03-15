# Destination

Struct in [BasicBlock](yarn.compiler.basicblock.md)

Inherits from `System.ValueType`

## Summary

A destination represents a [BasicBlock](yarn.compiler.basicblock.md) or node that may be run, following the execution of a [BasicBlock](yarn.compiler.basicblock.md) .

```csharp
public struct Destination
```

## Remarks

Destination objects represent links between blocks, or between blocks and nodes.

## Enums

| Name                                                                       | Description                |
| -------------------------------------------------------------------------- | -------------------------- |
| [DestinationType](yarn.compiler.basicblock.destination.destinationtype.md) | The type of a Destination. |

## Properties

| Name                                                           | Description                                                                  |
| -------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [Block](yarn.compiler.basicblock.destination.block.md)         | The block that this destination refers to.                                   |
| [Condition](yarn.compiler.basicblock.destination.condition.md) | The condition that causes this destination to be reached.                    |
| [NodeName](yarn.compiler.basicblock.destination.nodename.md)   | The name of the node that this destination refers to.                        |
| [Type](yarn.compiler.basicblock.destination.type.md)           | Gets the Destination's type - whether the destination is a block, or a node. |
