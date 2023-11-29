# BasicBlock

Class in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


A basic block is a run of instructions inside a Node. Basic blocks group
instructions up into segments such that execution only ever begins at
the start of a block (that is, a program never jumps into the middle of
a block), and execution only ever leaves at the end of a block.


```csharp
public class BasicBlock
```

## Classes

|Name|Description|
|:---|:---|
|[CommandElement](/api/csharp/yarn.compiler.basicblock.commandelement.md)|A command that will be executed.|
|[LineElement](/api/csharp/yarn.compiler.basicblock.lineelement.md)|A line of dialogue that should be shown to the player.|
|[OptionsElement](/api/csharp/yarn.compiler.basicblock.optionselement.md)|A collection of options that should be shown to the player.|
|[PlayerVisibleContentElement](/api/csharp/yarn.compiler.basicblock.playervisiblecontentelement.md)|An abstract class that represents some content that is shown to the player.|

## Enums

|Name|Description|
|:---|:---|
|[Condition](/api/csharp/yarn.compiler.basicblock.condition.md)|The conditions under which a  <a href="yarn.compiler.basicblock.destination.md">Destination</a>  may be reached at the end of a BasicBlock.|

## Methods

|Name|Description|
|:---|:---|
|[AddDestination(string,Condition)](/api/csharp/yarn.compiler.basicblock.adddestination-2.md)|Adds a new destination to this block, that points to a node.|
|[AddDestination(BasicBlock,Condition)](/api/csharp/yarn.compiler.basicblock.adddestination-1.md)|Adds a new destination to this block, that points to another block.|

## Properties

|Name|Description|
|:---|:---|
|[Ancestors](/api/csharp/yarn.compiler.basicblock.ancestors.md)|Get the ancestors of this block - that is, blocks that may run immediately before this block.|
|[Descendants](/api/csharp/yarn.compiler.basicblock.descendants.md)|Gets all descendants (that is, destinations, and destinations of those destinations, and so on), recursively.|
|[DescendantsWithPlayerVisibleContent](/api/csharp/yarn.compiler.basicblock.descendantswithplayervisiblecontent.md)|Gets all descendants (that is, destinations, and destinations of those destinations, and so on) that have any player-visible content, recursively.|
|[Destinations](/api/csharp/yarn.compiler.basicblock.destinations.md)|Gets the destinations of this block - that is, blocks or nodes that may run immediately after this block.|
|[FirstInstructionIndex](/api/csharp/yarn.compiler.basicblock.firstinstructionindex.md)|Gets the index of the first instruction of the node that this block is in.|
|[Instructions](/api/csharp/yarn.compiler.basicblock.instructions.md)|Gets the Instructions that form this block.|
|[LabelName](/api/csharp/yarn.compiler.basicblock.labelname.md)|Gets the name of the label that this block begins at, or null if this basic block does not begin at a labelled instruction.|
|[Name](/api/csharp/yarn.compiler.basicblock.name.md)|Gets a descriptive name for the block.|
|[NodeName](/api/csharp/yarn.compiler.basicblock.nodename.md)|Gets the name of the node that this block is in.|
|[PlayerVisibleContent](/api/csharp/yarn.compiler.basicblock.playervisiblecontent.md)|Gets the collection of player-visible content that will be delivered when this block is run.|

## Structs

|Name|Description|
|:---|:---|
|[Destination](/api/csharp/yarn.compiler.basicblock.destination.md)|A destination represents a  <a href="yarn.compiler.basicblock.md">BasicBlock</a>  or node that may be run, following the execution of a  <a href="yarn.compiler.basicblock.md">BasicBlock</a> .|

