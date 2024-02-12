# AddDestination(BasicBlock,Condition)

Method in [BasicBlock](./)

## Summary

Adds a new destination to this block, that points to another block.

```csharp
public void AddDestination(BasicBlock descendant, Condition condition)
```

## Parameters

| Name                                                                                | Description                                         |
| ----------------------------------------------------------------------------------- | --------------------------------------------------- |
| [Yarn.Compiler.BasicBlock](./) descendant                                           | The new descendant node.                            |
| [Yarn.Compiler.BasicBlock.Condition](yarn.compiler.basicblock.condition/) condition | The condition under which `descendant` will be run. |
