# Yarn Namespace

## Summary

Contains classes for working with compiled Yarn programs.

## Classes

| Name                                             | Description                                                                                                                |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| [BuiltinTypes](yarn.builtintypes/)               | Contains the built-in types available in the Yarn language.                                                                |
| [Dialogue](yarn.dialogue/)                       | Co-ordinates the execution of Yarn programs.                                                                               |
| [DialogueException](yarn.dialogueexception.md)   | An exception that is thrown by [Dialogue](yarn.dialogue/) when there is an error in executing a [Program](yarn.program/) . |
| [FunctionType](yarn.functiontype/)               | A type that represents functions.                                                                                          |
| [Header](yarn.header/)                           |                                                                                                                            |
| [Library](yarn.library/)                         | A collection of functions that can be called from Yarn programs.                                                           |
| [MemoryVariableStore](yarn.memoryvariablestore/) | A simple concrete implementation of [IVariableStorage](yarn.ivariablestorage/) that keeps all variables in memory.         |
| [Node](yarn.node/)                               | A node of Yarn script, contained within a [Program](yarn.program/) , and containing `Yarn.Instruction` s.                  |
| [Program](yarn.program/)                         | A compiled Yarn program.                                                                                                   |

## Delegates

| Name                                                       | Description                                                                                                     |
| ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| [CommandHandler](yarn.commandhandler.md)                   | Represents the method that is called when the Dialogue delivers a [Command](yarn.command/) .                    |
| [DialogueCompleteHandler](yarn.dialoguecompletehandler.md) | Represents the method that is called when the dialogue has reached its end, and no more code remains to be run. |
| [LineHandler](yarn.linehandler.md)                         | Represents the method that is called when the Dialogue delivers a [Line](yarn.line/) .                          |
| [Logger](yarn.logger.md)                                   | Represents a method that receives diagnostic messages and error information from a [Dialogue](yarn.dialogue/) . |
| [NodeCompleteHandler](yarn.nodecompletehandler.md)         | Represents the method that is called when the Dialogue reaches the end of a node.                               |
| [NodeStartHandler](yarn.nodestarthandler.md)               | Represents the method that is called when the Dialogue begins executing a node.                                 |
| [OptionsHandler](yarn.optionshandler.md)                   | Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset/) .               |
| [PrepareForLinesHandler](yarn.prepareforlineshandler.md)   | Represents the method that is called when the dialogue anticipates that it will deliver lines.                  |

## Interfaces

| Name                                       | Description                                                                          |
| ------------------------------------------ | ------------------------------------------------------------------------------------ |
| [IType](yarn.itype/)                       | Defines properties that describe a type in the Yarn language.                        |
| [IVariableStorage](yarn.ivariablestorage/) | Provides a mechanism for storing and retrieving instances of the `Yarn.Value` class. |

## Namespaces

| Name                               | Description                                                              |
| ---------------------------------- | ------------------------------------------------------------------------ |
| [Yarn.Compiler](../yarn.compiler/) | Contains classes for compiling Yarn code.                                |
| [Yarn.Markup](../yarn.markup/)     | Contains classes for working with markup in Yarn lines.                  |
| [Yarn.Unity](../yarn.unity/)       | Contains classes for working with Yarn Spinner in the Unity game engine. |

## Structs

| Name                         | Description                                                                                                       |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| [Command](yarn.command/)     | A command, sent from the [Dialogue](yarn.dialogue/) to the game.                                                  |
| [Line](yarn.line/)           | A line of dialogue, sent from the [Dialogue](yarn.dialogue/) to the game.                                         |
| [OptionSet](yarn.optionset/) | A set of [Option](yarn.optionset/yarn.optionset.option/) s, sent from the [Dialogue](yarn.dialogue/) to the game. |
