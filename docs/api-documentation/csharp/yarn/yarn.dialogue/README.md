# Dialogue

Class in [Yarn](../)

Inherits from `System.Object`

## Summary

Co-ordinates the execution of Yarn programs.

```csharp
public class Dialogue : IAttributeMarkerProcessor
```

## Constructors

| Name                                                      | Description                                             |
| --------------------------------------------------------- | ------------------------------------------------------- |
| [Dialogue(Yarn.IVariableStorage)](yarn.dialogue..ctor.md) | Initializes a new instance of the [Dialogue](./) class. |

## Fields

| Name                                                          | Description                              |
| ------------------------------------------------------------- | ---------------------------------------- |
| [DefaultStartNodeName](yarn.dialogue.defaultstartnodename.md) | The node that execution will start from. |

## Methods

| Name                                                                      | Description                                                                                                                         |
| ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [AddProgram(Program)](yarn.dialogue.addprogram.md)                        | Loads the nodes from the specified [Program](../yarn.program/) , and adds them to the nodes already loaded.                         |
| [Continue()](yarn.dialogue.continue.md)                                   | Starts, or continues, execution of the current Program.                                                                             |
| [ExpandSubstitutions(string,IList)](yarn.dialogue.expandsubstitutions.md) | Replaces all substitution markers in a text with the given substitution list.                                                       |
| [GetStringIDForNode(string)](yarn.dialogue.getstringidfornode.md)         | Returns the string ID that contains the original, uncompiled source text for a node.                                                |
| [GetTagsForNode(string)](yarn.dialogue.gettagsfornode.md)                 | Returns the tags for the node `nodeName` .                                                                                          |
| [NodeExists(string)](yarn.dialogue.nodeexists.md)                         | Gets a value indicating whether a specified node exists in the Program.                                                             |
| [ParseMarkup(string)](yarn.dialogue.parsemarkup.md)                       | Parses a line of text, and produces a [MarkupParseResult](../../yarn.markup/yarn.markup.markupparseresult/) containing the results. |
| [SetNode(string)](yarn.dialogue.setnode.md)                               | Prepares the [Dialogue](./) that the user intends to start running a node.                                                          |
| [SetProgram(Program)](yarn.dialogue.setprogram.md)                        | Loads all nodes from the provided [Program](../yarn.program/) .                                                                     |
| [SetSelectedOption(int)](yarn.dialogue.setselectedoption.md)              | Signals to the [Dialogue](./) that the user has selected a specified [Option](../yarn.optionset/yarn.optionset.option/) .           |
| [Stop()](yarn.dialogue.stop.md)                                           | Immediately stops the [Dialogue](./) .                                                                                              |
| [UnloadAll()](yarn.dialogue.unloadall.md)                                 | Unloads all nodes from the Dialogue.                                                                                                |

## Properties

| Name                                                                | Description                                                                                                                                            |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [CommandHandler](yarn.dialogue.commandhandler.md)                   | Gets or sets the [CommandHandler](../yarn.commandhandler.md) that is called when a command is to be delivered to the game.                             |
| [CurrentNode](yarn.dialogue.currentnode.md)                         | Gets the name of the node that this Dialogue is currently executing.                                                                                   |
| [DialogueCompleteHandler](yarn.dialogue.dialoguecompletehandler.md) | Gets or sets the [DialogueCompleteHandler](../yarn.dialoguecompletehandler.md) that is called when the dialogue reaches its end.                       |
| [IsActive](yarn.dialogue.isactive.md)                               | Gets a value indicating whether the Dialogue is currently executing Yarn instructions.                                                                 |
| [LanguageCode](yarn.dialogue.languagecode.md)                       | Gets or sets the [Dialogue](./) 's locale, as an IETF BCP 47 code.                                                                                     |
| [Library](yarn.dialogue.library.md)                                 | Gets the [Library](../yarn.library/) that this Dialogue uses to locate functions.                                                                      |
| [LineHandler](yarn.dialogue.linehandler.md)                         | Gets or sets the [LineHandler](../yarn.linehandler.md) that is called when a line is ready to be shown to the user.                                    |
| [LogDebugMessage](yarn.dialogue.logdebugmessage.md)                 | Invoked when the Dialogue needs to report debugging information.                                                                                       |
| [LogErrorMessage](yarn.dialogue.logerrormessage.md)                 | Invoked when the Dialogue needs to report an error.                                                                                                    |
| [NodeCompleteHandler](yarn.dialogue.nodecompletehandler.md)         | Gets or sets the [NodeCompleteHandler](../yarn.nodecompletehandler.md) that is called when a node is complete.                                         |
| [NodeNames](yarn.dialogue.nodenames.md)                             | Gets the names of the nodes in the currently loaded Program.                                                                                           |
| [NodeStartHandler](yarn.dialogue.nodestarthandler.md)               | Gets or sets the [NodeStartHandler](../yarn.nodestarthandler.md) that is called when a node is started.                                                |
| [OptionsHandler](yarn.dialogue.optionshandler.md)                   | Gets or sets the [OptionsHandler](../yarn.optionshandler.md) that is called when a set of options are ready to be shown to the user.                   |
| [PrepareForLinesHandler](yarn.dialogue.prepareforlineshandler.md)   | Gets or sets the [PrepareForLinesHandler](yarn.dialogue.prepareforlineshandler.md) that is called when the dialogue anticipates delivering some lines. |
| [VariableStorage](yarn.dialogue.variablestorage.md)                 | Gets or sets the object that provides access to storing and retrieving the values of variables.                                                        |
