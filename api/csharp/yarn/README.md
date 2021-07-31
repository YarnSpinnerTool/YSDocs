# Yarn Namespace

Contains classes for working with compiled Yarn programs.

## Structs

| Name | Description |
| :--- | :--- |
| [`Command`](command/) | A command, sent from the [`Dialogue`](dialogue/) to the game. |
| [`Line`](line/) | A line of dialogue, sent from the [`Dialogue`](dialogue/) to the game. |
| [`OptionSet`](optionset/) | A set of [`OptionSet.Option`](optionset.option/)s, sent from the [`Dialogue`](dialogue/) to the game. |
| [`OptionSet.Option`](optionset.option/) | An option to be presented to the user. |

## Delegates

| Name | Description |
| :--- | :--- |
| [`CommandHandler`](commandhandler.md) | Represents the method that is called when the Dialogue delivers a [`Command`](command/). |
| [`DialogueCompleteHandler`](dialoguecompletehandler.md) | Represents the method that is called when the dialogue has reached its end, and no more code remains to be run. |
| [`LineHandler`](linehandler.md) | Represents the method that is called when the Dialogue delivers a [`Line`](line/). |
| [`Logger`](logger.md) | Represents a method that receives diagnostic messages and error information from a [`Dialogue`](dialogue/). |
| [`NodeCompleteHandler`](nodecompletehandler.md) | Represents the method that is called when the Dialogue reaches the end of a node. |
| [`NodeStartHandler`](nodestarthandler.md) | Represents the method that is called when the Dialogue begins executing a node. |
| [`OptionsHandler`](optionshandler.md) | Represents the method that is called when the Dialogue delivers an [`OptionSet`](optionset/). |
| [`PrepareForLinesHandler`](prepareforlineshandler.md) | Represents the method that is called when the dialogue anticipates that it will deliver lines. |

## Classes

| Name | Description |
| :--- | :--- |
| [`Dialogue`](dialogue/) | Co-ordinates the execution of Yarn programs. |
| [`DialogueException`](dialogueexception.md) | An exception that is thrown by [`Dialogue`](dialogue/) when there is an error in executing a [`Program`](program/). |
| [`Instruction`](instruction/) | An instruction in a Yarn Program. |
| [`Instruction.Types`](instruction.types.md) | Container for nested types declared in the Instruction message type. |
| [`Library`](library/) | A collection of functions that can be called from Yarn programs. |
| [`MemoryVariableStore`](memoryvariablestore/) | A simple concrete implementation of [`IVariableStorage`](ivariablestorage/) that keeps all variables in memory. |
| [`Node`](node/) | A \[node\]\(\), contained within a [`Program`](program/), and containing [`Instruction`](instruction/)s. |
| [`Operand`](operand/) | A value used by an Instruction. |
| [`Program`](program/) | A compiled Yarn program. |

## Enums

| Name | Description |
| :--- | :--- |
| [`Instruction.Types.OpCode`](instruction.types.opcode/) | The type of instruction that this is. |
| [`Operand.ValueOneofCase`](operand.valueoneofcase/) | Enum of possible cases for the "value" oneof. |
| [`Type`](type/) | The type of a `Yarn.Value`. |

## Interfaces

| Name | Description |
| :--- | :--- |
| [`IVariableStorage`](ivariablestorage/) | Provides a mechanism for storing and retrieving instances of the `Yarn.Value` class. |

