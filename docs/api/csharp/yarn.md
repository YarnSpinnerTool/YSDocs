# Yarn Namespace

## Summary

Contains classes for working with compiled Yarn programs.


## Classes

|Name|Description|
|:---|:---|
|[ConstantTypeProperty](/docs/api/csharp/yarn.constanttypeproperty.md)|Represents a property that belongs to a type and contains a read-only value.|
|[Dialogue](/docs/api/csharp/yarn.dialogue.md)|Co-ordinates the execution of Yarn programs.|
|[DialogueException](/docs/api/csharp/yarn.dialogueexception.md)|An exception that is thrown by  [Dialogue](yarn.dialogue.md)  when there is an error in executing a  [Program](yarn.program.md) .|
|[EnumBase](/docs/api/csharp/yarn.enumbase.md)|The base type for all enumeration types.|
|[EnumType](/docs/api/csharp/yarn.enumtype.md)|A type that represents enumerations.|
|[FunctionType](/docs/api/csharp/yarn.functiontype.md)|A type that represents a function.|
|[Header](/docs/api/csharp/yarn.header.md)||
|[Library](/docs/api/csharp/yarn.library.md)|A collection of functions that can be called from Yarn programs.|
|[MemoryVariableStore](/docs/api/csharp/yarn.memoryvariablestore.md)|A simple concrete implementation of  [IVariableStorage](yarn.ivariablestorage.md)  that keeps all variables in memory.|
|[Node](/docs/api/csharp/yarn.node.md)|A node of Yarn script, contained within a  [Program](yarn.program.md) , and containing  `Yarn.Instruction` s.|
|[Program](/docs/api/csharp/yarn.program.md)|A compiled Yarn program.|
|[TypeBase](/docs/api/csharp/yarn.typebase.md)|Provides the base class for all concrete types.|
|[Types](/docs/api/csharp/yarn.types.md)|Contains the built-in types available in the Yarn language.|

## Delegates

|Name|Description|
|:---|:---|
|[CommandHandler](/docs/api/csharp/yarn.commandhandler.md)|Represents the method that is called when the Dialogue delivers a  [Command](yarn.command.md) .|
|[DialogueCompleteHandler](/docs/api/csharp/yarn.dialoguecompletehandler.md)|Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.|
|[LineHandler](/docs/api/csharp/yarn.linehandler.md)|Represents the method that is called when the Dialogue delivers a  [Line](yarn.line.md) .|
|[Logger](/docs/api/csharp/yarn.logger.md)|Represents a method that receives diagnostic messages and error information from a  [Dialogue](yarn.dialogue.md) .|
|[NodeCompleteHandler](/docs/api/csharp/yarn.nodecompletehandler.md)|Represents the method that is called when the Dialogue reaches the end of a node.|
|[NodeStartHandler](/docs/api/csharp/yarn.nodestarthandler.md)|Represents the method that is called when the Dialogue begins executing a node.|
|[OptionsHandler](/docs/api/csharp/yarn.optionshandler.md)|Represents the method that is called when the Dialogue delivers an  [OptionSet](yarn.optionset.md) .|
|[PrepareForLinesHandler](/docs/api/csharp/yarn.prepareforlineshandler.md)|Represents the method that is called when the dialogue anticipates that it will deliver lines.|

## Enums

|Name|Description|
|:---|:---|
|[VariableKind](/docs/api/csharp/yarn.variablekind.md)|Represents different kinds of variables that can be fetched from a  [TryGetValue(string,T?)](yarn.dialogue.md">Dialogue</a>  using  <a href="yarn.ivariableaccess.trygetvalue.md) .|

## Interfaces

|Name|Description|
|:---|:---|
|[IMarkupParser](/docs/api/csharp/yarn.imarkupparser.md)|Contains methods for parsing raw text into a  [MarkupParseResult](yarn.markup.markupparseresult.md) .|
|[ISmartVariableEvaluator](/docs/api/csharp/yarn.ismartvariableevaluator.md)|Contains methods for evaluating the value of smart variables|
|[IType](/docs/api/csharp/yarn.itype.md)|Defines properties that describe a type in the Yarn language.|
|[ITypeMember](/docs/api/csharp/yarn.itypemember.md)|Provides properties used to work with members of a type.|
|[IVariableAccess](/docs/api/csharp/yarn.ivariableaccess.md)|Provides a mechanism for retrieving values.|
|[IVariableStorage](/docs/api/csharp/yarn.ivariablestorage.md)|Provides a mechanism for storing values.|
|[IYarnValue](/docs/api/csharp/yarn.iyarnvalue.md)|Represents a read-only value in the Yarn Spinner virtual machine.|

## Namespaces

|Name|Description|
|:---|:---|
|[Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)|Contains classes for compiling Yarn code.|
|[Yarn.Markup](/docs/api/csharp/yarn.markup.md)|Contains classes for working with markup in Yarn lines.|
|[Yarn.Saliency](/docs/api/csharp/yarn.saliency.md)|Contains classes for choosing the most relevant content out of a set of possible options.|
|[Yarn.Unity](/docs/api/csharp/yarn.unity.md)|Contains classes for working with Yarn Spinner in the Unity game engine.|
|[Yarn.Utility](/docs/api/csharp/yarn.utility.md)|Contains utility classes used by Yarn Spinner.|

## Structs

|Name|Description|
|:---|:---|
|[Command](/docs/api/csharp/yarn.command.md)|A command, sent from the  [Dialogue](yarn.dialogue.md)  to the game.|
|[Line](/docs/api/csharp/yarn.line.md)|A line of dialogue, sent from the  [Dialogue](yarn.dialogue.md)  to the game.|
|[OptionSet](/docs/api/csharp/yarn.optionset.md)|A set of  [Dialogue](yarn.optionset.option.md">Option</a> s, sent from the  <a href="yarn.dialogue.md)  to the game.|

