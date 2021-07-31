# Dialogue

Co-ordinates the execution of Yarn programs.

```csharp
public class Dialogue : IAttributeMarkerProcessor
```

## Constructors

| Name | Description |
| :--- | :--- |
| [`Dialogue(IVariableStorage)`](dialogue._ctor-ivariablestorage.md) | Initializes a new instance of the [`Dialogue`](./) class. |

## Methods

| Name | Description |
| :--- | :--- |
| [`AddProgram(Program)`](dialogue.addprogram-program.md) | Loads the nodes from the specified [`Program`](../program/), and adds them to the nodes already loaded. |
| [`Continue()`](dialogue.continue.md) | Starts, or continues, execution of the current Program. |
| [`ExpandSubstitutions(String, IList<String>)`](dialogue.expandsubstitutions-system.string-system.collections.generic.ilist-system.string.md) | Replaces all substitution markers in a text with the given substitution list. |
| [`GetStringIDForNode(String)`](dialogue.getstringidfornode-system.string.md) | Returns the string ID that contains the original, uncompiled source text for a node. |
| [`GetTagsForNode(String)`](dialogue.gettagsfornode-system.string.md) | Returns the tags for the node 'nodeName'. |
| [`NodeExists(String)`](dialogue.nodeexists-system.string.md) | Gets a value indicating whether a specified node exists in the Program. |
| [`ParseMarkup(String)`](dialogue.parsemarkup-system.string.md) | Parses a line of text, and produces a [`MarkupParseResult`](../../yarn.markup/markupparseresult/) containing the results. |
| [`SetNode(String)`](dialogue.setnode-system.string.md) | Prepares the [`Dialogue`](./) that the user intends to start running a node. |
| [`SetProgram(Program)`](dialogue.setprogram-program.md) | Loads all nodes from the provided [`Program`](../program/). |
| [`SetSelectedOption(Int32)`](dialogue.setselectedoption-system.int32.md) | Signals to the [`Dialogue`](./) that the user has selected a specified [`OptionSet.Option`](../optionset.option/). |
| [`Stop()`](dialogue.stop.md) | Immediately stops the [`Dialogue`](./). |
| [`UnloadAll()`](dialogue.unloadall.md) | Unloads all nodes from the Dialogue. |

## Properties

| Name | Description |
| :--- | :--- |
| [`CommandHandler`](dialogue.commandhandler.md) | Gets or sets the [`CommandHandler`](../commandhandler.md) that is called when a command is to be delivered to the game. |
| [`CurrentNode`](dialogue.currentnode.md) | Gets the name of the node that this Dialogue is currently executing. |
| [`DialogueCompleteHandler`](dialogue.dialoguecompletehandler.md) | Gets or sets the [`DialogueCompleteHandler`](../dialoguecompletehandler.md) that is called when the dialogue reaches its end. |
| [`IsActive`](dialogue.isactive.md) | Gets a value indicating whether the Dialogue is currently executing Yarn instructions. |
| [`LanguageCode`](dialogue.languagecode.md) | Gets or sets the [`Dialogue`](./)'s locale, as an IETF BCP 47 code. |
| [`Library`](dialogue.library.md) | Gets the [`Library`](../library/) that this Dialogue uses to locate functions. |
| [`LineHandler`](dialogue.linehandler.md) | Gets or sets the [`LineHandler`](../linehandler.md) that is called when a line is ready to be shown to the user. |
| [`LogDebugMessage`](dialogue.logdebugmessage.md) | Invoked when the Dialogue needs to report debugging information. |
| [`LogErrorMessage`](dialogue.logerrormessage.md) | Invoked when the Dialogue needs to report an error. |
| [`NodeCompleteHandler`](dialogue.nodecompletehandler.md) | Gets or sets the [`NodeCompleteHandler`](../nodecompletehandler.md) that is called when a node is complete. |
| [`NodeNames`](dialogue.nodenames.md) | Gets the names of the nodes in the currently loaded Program. |
| [`NodeStartHandler`](dialogue.nodestarthandler.md) | Gets or sets the [`NodeStartHandler`](../nodestarthandler.md) that is called when a node is started. |
| [`OptionsHandler`](dialogue.optionshandler.md) | Gets or sets the [`OptionsHandler`](../optionshandler.md) that is called when a set of options are ready to be shown to the user. |
| [`PrepareForLinesHandler`](dialogue.prepareforlineshandler.md) | Gets or sets the [`PrepareForLinesHandler`](dialogue.prepareforlineshandler.md) that is called when the dialogue anticipates delivering some lines. |

## Fields

| Name | Description |
| :--- | :--- |
| [`DefaultStartNodeName`](dialogue.defaultstartnodename.md) | The node that execution will start from. |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L391), line 391.

