# Node

A \[node\]\(\), contained within a [`Program`](../program/), and containing [`Instruction`](../instruction/)s.

```csharp
public sealed class Node : IMessage<Node>, IMessage, IEquatable<Node>, IDeepCloneable<Node>
```

## Properties

| Name | Description |
| :--- | :--- |
| [`Instructions`](node.instructions.md) | The list of instructions in this node. |
| [`Labels`](node.labels.md) | A jump table, mapping the names of labels to positions in the instructions list. |
| [`Name`](node.name.md) | The name of this node. |
| [`SourceTextStringID`](node.sourcetextstringid.md) | the entry in the program's string table that contains the original text of this node; null if this is not available |
| [`Tags`](node.tags.md) | The tags associated with this node. |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L247), line 247.

