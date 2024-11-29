# BasicBlock.AddDestination(BasicBlock,Condition,string?)

Method in [BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md)

## Summary


Adds a new destination to this block that points to a node, with a
option's line ID for context.


```csharp
public void AddDestination(BasicBlock descendant, Condition condition, string? lineID)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Compiler.BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md) descendant|The new descendant node.|
|[Yarn.Compiler.BasicBlock.Condition](/docs/api/csharp/yarn.compiler.basicblock.condition.md) condition|The condition under which the node  <code>descendant</code>  will be run.|
|`string` lineID|The line ID of the option that must be selected in order for  <code>descendant</code>  to run.|

