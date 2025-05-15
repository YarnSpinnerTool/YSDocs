# NodeDestination(string,Condition,BasicBlock?)

Constructor in [NodeDestination](/docs/api/csharp/yarn.compiler.basicblock.nodedestination.md)

## Summary


Initialises a new instance of the  [NodeDestination](yarn.compiler.basicblock.nodedestination.md) 
class.


```csharp
public NodeDestination(string nodeName, Condition condition, BasicBlock? returnTo = null)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Compiler.BasicBlock.Condition](/docs/api/csharp/yarn.compiler.basicblock.condition.md) condition|The condition under which the destination will be run.|
|[Yarn.Compiler.BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md) returnTo|An optional block that may be returned to later in the program execution.|
|`string` nodeName|The name of the node to jump or detour to.|

