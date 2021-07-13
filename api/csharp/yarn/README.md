# Yarn Namespace
Contains classes for working with compiled Yarn programs.
## Structs
|Name|Description|
|:---|:---|
|[`Command`](/api/csharp/yarn/command.md)| A command, sent from the [`Dialogue`](/api/csharp/yarn/dialogue.md) to the game. |
|[`Line`](/api/csharp/yarn/line.md)| A line of dialogue, sent from the [`Dialogue`](/api/csharp/yarn/dialogue.md) to the game. |
|[`OptionSet`](/api/csharp/yarn/optionset.md)| A set of [`OptionSet.Option`](/api/csharp/yarn/optionset.option.md)s, sent from the [`Dialogue`](/api/csharp/yarn/dialogue.md) to the game. |
|[`OptionSet.Option`](/api/csharp/yarn/optionset.option.md)| An option to be presented to the user. |
## Delegates
|Name|Description|
|:---|:---|
|[`CommandHandler`](/api/csharp/yarn/commandhandler.md)| Represents the method that is called when the Dialogue delivers a [`Command`](/api/csharp/yarn/command.md). |
|[`DialogueCompleteHandler`](/api/csharp/yarn/dialoguecompletehandler.md)| Represents the method that is called when the dialogue has reached its end, and no more code remains to be run. |
|[`LineHandler`](/api/csharp/yarn/linehandler.md)| Represents the method that is called when the Dialogue delivers a [`Line`](/api/csharp/yarn/line.md). |
|[`Logger`](/api/csharp/yarn/logger.md)| Represents a method that receives diagnostic messages and error information from a [`Dialogue`](/api/csharp/yarn/dialogue.md). |
|[`NodeCompleteHandler`](/api/csharp/yarn/nodecompletehandler.md)| Represents the method that is called when the Dialogue reaches the end of a node. |
|[`NodeStartHandler`](/api/csharp/yarn/nodestarthandler.md)| Represents the method that is called when the Dialogue begins executing a node. |
|[`OptionsHandler`](/api/csharp/yarn/optionshandler.md)| Represents the method that is called when the Dialogue delivers an [`OptionSet`](/api/csharp/yarn/optionset.md). |
|[`PrepareForLinesHandler`](/api/csharp/yarn/prepareforlineshandler.md)| Represents the method that is called when the dialogue anticipates that it will deliver lines. |
## Classes
|Name|Description|
|:---|:---|
|[`Dialogue`](/api/csharp/yarn/dialogue.md)| Co-ordinates the execution of Yarn programs. |
|[`DialogueException`](/api/csharp/yarn/dialogueexception.md)| An exception that is thrown by [`Dialogue`](/api/csharp/yarn/dialogue.md) when there is an error in executing a [`Program`](/api/csharp/yarn/program.md). |
|[`Instruction`](/api/csharp/yarn/instruction.md)| An instruction in a Yarn Program. |
|[`Instruction.Types`](/api/csharp/yarn/instruction.types.md)|Container for nested types declared in the Instruction message type.|
|[`Library`](/api/csharp/yarn/library.md)| A collection of functions that can be called from Yarn programs. |
|[`MemoryVariableStore`](/api/csharp/yarn/memoryvariablestore.md)| A simple concrete implementation of [`IVariableStorage`](/api/csharp/yarn/ivariablestorage.md) that keeps all variables in memory. |
|[`Node`](/api/csharp/yarn/node.md)| A [node]({{<ref "/docs/writing/nodes-and-content.md#nodes">}}), contained within a [`Program`](/api/csharp/yarn/program.md), and containing [`Instruction`](/api/csharp/yarn/instruction.md)s. |
|[`Operand`](/api/csharp/yarn/operand.md)| A value used by an Instruction. |
|[`Program`](/api/csharp/yarn/program.md)| A compiled Yarn program. |
## Enums
|Name|Description|
|:---|:---|
|[`Instruction.Types.OpCode`](/api/csharp/yarn/instruction.types.opcode.md)| The type of instruction that this is. |
|[`Operand.ValueOneofCase`](/api/csharp/yarn/operand.valueoneofcase.md)|Enum of possible cases for the "value" oneof.|
|[`Type`](/api/csharp/yarn/type.md)| The type of a `Yarn.Value`. |
## Interfaces
|Name|Description|
|:---|:---|
|[`IVariableStorage`](/api/csharp/yarn/ivariablestorage.md)|Provides a mechanism for storing and retrieving instances of the `Yarn.Value` class.|
