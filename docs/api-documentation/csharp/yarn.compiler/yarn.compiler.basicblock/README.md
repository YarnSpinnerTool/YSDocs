# BasicBlock

Class in [Yarn.Compiler](../)

Inherits from `System.Object`

## Summary

A basic block is a run of instructions inside a Node. Basic blocks group instructions up into segments such that execution only ever begins at the start of a block (that is, a program never jumps into the middle of a block), and execution only ever leaves at the end of a block.

```csharp
public class BasicBlock
```

## Classes

| Name                                                                                   | Description                                                                 |
| -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| [CommandElement](yarn.compiler.basicblock.commandelement/)                             | A command that will be executed.                                            |
| [LineElement](yarn.compiler.basicblock.lineelement/)                                   | A line of dialogue that should be shown to the player.                      |
| [OptionsElement](yarn.compiler.basicblock.optionselement/)                             | A collection of options that should be shown to the player.                 |
| [PlayerVisibleContentElement](yarn.compiler.basicblock.playervisiblecontentelement.md) | An abstract class that represents some content that is shown to the player. |

## Enums

| Name                                             | Description                                                                                                                  |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| [Condition](yarn.compiler.basicblock.condition/) | The conditions under which a [Destination](yarn.compiler.basicblock.destination/) may be reached at the end of a BasicBlock. |

## Methods

| Name                                                                                 | Description                                                         |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| [AddDestination(string,Condition)](yarn.compiler.basicblock.adddestination-2.md)     | Adds a new destination to this block, that points to a node.        |
| [AddDestination(BasicBlock,Condition)](yarn.compiler.basicblock.adddestination-1.md) | Adds a new destination to this block, that points to another block. |

## Properties

| Name                                                                                                   | Description                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Ancestors](yarn.compiler.basicblock.ancestors.md)                                                     | Get the ancestors of this block - that is, blocks that may run immediately before this block.                                                      |
| [Descendants](yarn.compiler.basicblock.descendants.md)                                                 | Gets all descendants (that is, destinations, and destinations of those destinations, and so on), recursively.                                      |
| [DescendantsWithPlayerVisibleContent](yarn.compiler.basicblock.descendantswithplayervisiblecontent.md) | Gets all descendants (that is, destinations, and destinations of those destinations, and so on) that have any player-visible content, recursively. |
| [Destinations](yarn.compiler.basicblock.destinations.md)                                               | Gets the destinations of this block - that is, blocks or nodes that may run immediately after this block.                                          |
| [FirstInstructionIndex](yarn.compiler.basicblock.firstinstructionindex.md)                             | Gets the index of the first instruction of the node that this block is in.                                                                         |
| [Instructions](yarn.compiler.basicblock.instructions.md)                                               | Gets the Instructions that form this block.                                                                                                        |
| [LabelName](yarn.compiler.basicblock.labelname.md)                                                     | Gets the name of the label that this block begins at, or null if this basic block does not begin at a labelled instruction.                        |
| [Name](yarn.compiler.basicblock.name.md)                                                               | Gets a descriptive name for the block.                                                                                                             |
| [NodeName](yarn.compiler.basicblock.nodename.md)                                                       | Gets the name of the node that this block is in.                                                                                                   |
| [PlayerVisibleContent](yarn.compiler.basicblock.playervisiblecontent.md)                               | Gets the collection of player-visible content that will be delivered when this block is run.                                                       |

## Structs

| Name                                                 | Description                                                                                                          |
| ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| [Destination](yarn.compiler.basicblock.destination/) | A destination represents a [BasicBlock](./) or node that may be run, following the execution of a [BasicBlock](./) . |
