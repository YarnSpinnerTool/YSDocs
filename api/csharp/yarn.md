# Yarn Namespace

## Summary

Contains classes for working with compiled Yarn programs.


## Classes

|Name|Description|
|:---|:---|
|[BuiltinTypes](/api/csharp/yarn.builtintypes.md)|Contains the built-in types available in the Yarn language.|
|[Dialogue](/api/csharp/yarn.dialogue.md)|Co-ordinates the execution of Yarn programs.|
|[DialogueException](/api/csharp/yarn.dialogueexception.md)|An exception that is thrown by  <a href="yarn.dialogue.md">Dialogue</a>  when there is an error in executing a  <a href="yarn.program.md">Program</a> .|
|[FunctionType](/api/csharp/yarn.functiontype.md)|A type that represents functions.|
|[Library](/api/csharp/yarn.library.md)|A collection of functions that can be called from Yarn programs.|
|[MemoryVariableStore](/api/csharp/yarn.memoryvariablestore.md)|A simple concrete implementation of  <a href="yarn.ivariablestorage.md">IVariableStorage</a>  that keeps all variables in memory.|
|[Node](/api/csharp/yarn.node.md)|A node of Yarn script, contained within a  <a href="yarn.program.md">Program</a> , and containing  <code>Yarn.Instruction</code> s.|
|[Program](/api/csharp/yarn.program.md)|A compiled Yarn program.|

## Delegates

|Name|Description|
|:---|:---|
|[CommandHandler](/api/csharp/yarn.commandhandler.md)|Represents the method that is called when the Dialogue delivers a  <a href="yarn.command.md">Command</a> .|
|[DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md)|Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.|
|[LineHandler](/api/csharp/yarn.linehandler.md)|Represents the method that is called when the Dialogue delivers a  <a href="yarn.line.md">Line</a> .|
|[Logger](/api/csharp/yarn.logger.md)|Represents a method that receives diagnostic messages and error information from a  <a href="yarn.dialogue.md">Dialogue</a> .|
|[NodeCompleteHandler](/api/csharp/yarn.nodecompletehandler.md)|Represents the method that is called when the Dialogue reaches the end of a node.|
|[NodeStartHandler](/api/csharp/yarn.nodestarthandler.md)|Represents the method that is called when the Dialogue begins executing a node.|
|[OptionsHandler](/api/csharp/yarn.optionshandler.md)|Represents the method that is called when the Dialogue delivers an  <a href="yarn.optionset.md">OptionSet</a> .|
|[PrepareForLinesHandler](/api/csharp/yarn.prepareforlineshandler.md)|Represents the method that is called when the dialogue anticipates that it will deliver lines.|

## Interfaces

|Name|Description|
|:---|:---|
|[IType](/api/csharp/yarn.itype.md)|Defines properties that describe a type in the Yarn language.|
|[IVariableStorage](/api/csharp/yarn.ivariablestorage.md)|Provides a mechanism for storing and retrieving instances of the  <code>Yarn.Value</code>  class.|

## Structs

|Name|Description|
|:---|:---|
|[Command](/api/csharp/yarn.command.md)|A command, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.|
|[Line](/api/csharp/yarn.line.md)|A line of dialogue, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.|
|[OptionSet](/api/csharp/yarn.optionset.md)|A set of  <a href="yarn.optionset.option.md">Option</a> s, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.|

## TYPENAME_UNKNOWN_PLURAL

|Name|Description|
|:---|:---|
|[Yarn.Compiler](/api/csharp/yarn.compiler.md)|Contains classes for compiling Yarn code.|
|[Yarn.Markup](/api/csharp/yarn.markup.md)|Contains classes for working with markup in Yarn lines.|
|[Yarn.Unity](/api/csharp/yarn.unity.md)|Contains classes for working with Yarn Spinner in the Unity game engine.|

