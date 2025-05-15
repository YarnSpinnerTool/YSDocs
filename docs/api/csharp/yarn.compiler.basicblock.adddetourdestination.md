# BasicBlock.AddDetourDestination(string,Condition,BasicBlock)

Method in [BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md)

## Summary


Adds a new destination to this block that represents a detour to a
node.


```csharp
public void AddDetourDestination(string nodeName, Condition condition, BasicBlock returnToBlock)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` nodeName|The name of the destination node.|
|[Yarn.Compiler.BasicBlock.Condition](/docs/api/csharp/yarn.compiler.basicblock.condition.md) condition|The condition under which  `nodeName`  will be jumped to.|
|[Yarn.Compiler.BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md) returnToBlock|The name of the block that will be returned to when the detour returns.|

