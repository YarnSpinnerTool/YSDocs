# BasicBlock.AddDestination(string,Condition)

Method in [BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md)

## Summary


Adds a new destination to this block, that points to a node.


```csharp
public void AddDestination(string nodeName, Condition condition)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` nodeName|The name of the destination node.|
|[Yarn.Compiler.BasicBlock.Condition](/docs/api/csharp/yarn.compiler.basicblock.condition.md) condition|The condition under which  <code>descendant</code>  will be run.|

