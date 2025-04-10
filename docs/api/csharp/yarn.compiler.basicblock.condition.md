# Condition

Enum in [BasicBlock](yarn.compiler.basicblock.md)

Inherits from `System.Enum`

## Summary

The conditions under which a [Destination](yarn.compiler.basicblock.destination.md) may be reached at the end of a BasicBlock.

```csharp
public enum Condition
{
    Fallthrough,
    DirectJump,
    ExpressionIsTrue,
    ExpressionIsFalse,
    Option
}
```

## Members

| Name                                                                         | Description                                                                                                                                                    |
| ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DirectJump](yarn.compiler.basicblock.condition.directjump.md)               | The Destination is reached beacuse of an explicit instruction to go to this block or node.                                                                     |
| [ExpressionIsFalse](yarn.compiler.basicblock.condition.expressionisfalse.md) | The Destination is reached because an expression evaluated to false.                                                                                           |
| [ExpressionIsTrue](yarn.compiler.basicblock.condition.expressionistrue.md)   | The Destination is reached because an expression evaluated to true.                                                                                            |
| [Fallthrough](yarn.compiler.basicblock.condition.fallthrough.md)             | The Destination is reached because the preceding BasicBlock reached the end of its execution, and the Destination's target is the block immediately following. |
| [Option](yarn.compiler.basicblock.condition.option.md)                       | The Destination is reached because the player made an in-game choice to go to it.                                                                              |
