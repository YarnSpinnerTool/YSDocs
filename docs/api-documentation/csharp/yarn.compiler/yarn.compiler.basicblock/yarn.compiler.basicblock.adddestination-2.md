# AddDestination(string,Condition)

Method in [BasicBlock](./)

## Summary

Adds a new destination to this block, that points to a node.

```csharp
public void AddDestination(string nodeName, Condition condition)
```

## Parameters

| Name                                                                                | Description                                         |
| ----------------------------------------------------------------------------------- | --------------------------------------------------- |
| `string` nodeName                                                                   | The name of the destination node.                   |
| [Yarn.Compiler.BasicBlock.Condition](yarn.compiler.basicblock.condition/) condition | The condition under which `descendant` will be run. |
