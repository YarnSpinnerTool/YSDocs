# Destination

Struct in [BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md)

Inherits from `System.ValueType`

## Summary


A destination represents a  <a href="yarn.compiler.basicblock.md">BasicBlock</a>  or node that may
be run, following the execution of a  <a href="yarn.compiler.basicblock.md">BasicBlock</a> .


```csharp
public struct Destination
```

## Remarks


Destination objects represent links between blocks, or between
blocks and nodes.


## Enums

|Name|Description|
|:---|:---|
|[DestinationType](/docs/api/csharp/yarn.compiler.basicblock.destination.destinationtype.md)|The type of a Destination.|

## Properties

|Name|Description|
|:---|:---|
|[Block](/docs/api/csharp/yarn.compiler.basicblock.destination.block.md)|The block that this destination refers to.|
|[Condition](/docs/api/csharp/yarn.compiler.basicblock.destination.condition.md)|The condition that causes this destination to be reached.|
|[NodeName](/docs/api/csharp/yarn.compiler.basicblock.destination.nodename.md)|The name of the node that this destination refers to.|
|[Type](/docs/api/csharp/yarn.compiler.basicblock.destination.type.md)|Gets the Destination's type - whether the destination is a block, or a node.|

