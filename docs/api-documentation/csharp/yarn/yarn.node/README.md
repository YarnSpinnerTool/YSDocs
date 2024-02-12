# Node

Class in [Yarn](../)

Inherits from `System.Object`

## Summary

A node of Yarn script, contained within a [Program](../yarn.program/) , and containing `Yarn.Instruction` s.

```csharp
public class Node
```

## Methods

| Name                                | Description |
| ----------------------------------- | ----------- |
| [ToString()](yarn.node.tostring.md) |             |

## Properties

| Name                                                  | Description                                                                                                         |
| ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| [Headers](yarn.node.headers.md)                       |                                                                                                                     |
| [Instructions](yarn.node.instructions.md)             | The list of instructions in this node.                                                                              |
| [Labels](yarn.node.labels.md)                         | A jump table, mapping the names of labels to positions in the instructions list.                                    |
| [Name](yarn.node.name.md)                             | The name of this node.                                                                                              |
| [SourceTextStringID](yarn.node.sourcetextstringid.md) | the entry in the program's string table that contains the original text of this node; null if this is not available |
| [Tags](yarn.node.tags.md)                             | The tags associated with this node.                                                                                 |
