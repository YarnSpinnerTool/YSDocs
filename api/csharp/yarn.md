# Yarn

## Summary

(not documented)

```csharp
namespace Yarn
{
    using System;
    using System.Collections.Generic;
    using System.IO;
    using System.Text.RegularExpressions;
    using Yarn.Markup;
}
```

## Types

|Name|Description|
|:---|:---|
|[Line](/api/csharp/yarn.line.md)|A line of dialogue, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.|
|[OptionSet](/api/csharp/yarn.optionset.md)|A set of  <a href="yarn.optionset.option.md">Option</a> s, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.|
|[Command](/api/csharp/yarn.command.md)|A command, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.|
|[Logger](/api/csharp/yarn.logger.md)|Represents a method that receives diagnostic messages and error information from a  <a href="yarn.dialogue.md">Dialogue</a> .|
|[IVariableStorage](/api/csharp/yarn.ivariablestorage.md)|Provides a mechanism for storing and retrieving instances of the  <code>T:Yarn.Value</code>  class.|
|[MemoryVariableStore](/api/csharp/yarn.memoryvariablestore.md)|A simple concrete implementation of  <a href="yarn.ivariablestorage.md">IVariableStorage</a>  that keeps all variables in memory.|
|[LineHandler](/api/csharp/yarn.linehandler.md)|Represents the method that is called when the Dialogue delivers a <a href="yarn.line.md">Line</a> .|
|[OptionsHandler](/api/csharp/yarn.optionshandler.md)|Represents the method that is called when the Dialogue delivers an <a href="yarn.optionset.md">OptionSet</a> .|
|[CommandHandler](/api/csharp/yarn.commandhandler.md)|Represents the method that is called when the Dialogue delivers a <a href="yarn.command.md">Command</a> .|
|[NodeCompleteHandler](/api/csharp/yarn.nodecompletehandler.md)|Represents the method that is called when the Dialogue reaches the end of a node.|
|[NodeStartHandler](/api/csharp/yarn.nodestarthandler.md)|Represents the method that is called when the Dialogue begins executing a node.|
|[DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md)|Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.|
|[PrepareForLinesHandler](/api/csharp/yarn.prepareforlineshandler.md)|Represents the method that is called when the dialogue anticipates that it will deliver lines.|
|[Dialogue](/api/csharp/yarn.dialogue.md)|Co-ordinates the execution of Yarn programs.|
|[DialogueException](/api/csharp/yarn.dialogueexception.md)|An exception that is thrown by  <a href="yarn.dialogue.md">Dialogue</a>  when there is an error in executing a  <a href="yarn.program.md">Program</a> .|
|[Library](/api/csharp/yarn.library.md)|A collection of functions that can be called from Yarn programs.|
|[Program](/api/csharp/yarn.program.md)|A compiled Yarn program.|
|[Node](/api/csharp/yarn.node.md)|A [node]({{|ref "/docs/writing/nodes-and-content.md#nodes"|}}), contained within a  <a href="yarn.program.md">Program</a> , and containing  <code>T:Yarn.Instruction</code> s.|
|[BuiltinTypes](/api/csharp/yarn.builtintypes.md)|Contains the built-in types available in the Yarn language.|
|[FunctionType](/api/csharp/yarn.functiontype.md)|A type that represents functions.|
|[IType](/api/csharp/yarn.itype.md)|Defines properties that describe a type in the Yarn language.|

## Namespaces

|Name|Description|
|:---|:---|
|[Yarn.Markup](/api/csharp/yarn.markup.md)|(not documented)|

