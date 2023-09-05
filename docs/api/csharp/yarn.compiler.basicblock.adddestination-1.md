# BasicBlock.AddDestination(BasicBlock,Condition)

Method in [BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md)

## Summary


Adds a new destination to this block, that points to another block.


```csharp
public void AddDestination(BasicBlock descendant, Condition condition)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Compiler.BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md) descendant|The new descendant node.|
|[Yarn.Compiler.BasicBlock.Condition](/docs/api/csharp/yarn.compiler.basicblock.condition.md) condition|The condition under which  <code>descendant</code>  will be run.|

