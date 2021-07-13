# Dialogue Class

Co-ordinates the execution of Yarn programs.


```csharp
public class Dialogue : IAttributeMarkerProcessor
```



## Constructors
|Name|Description|
|:---|:---|
|[`Dialogue(IVariableStorage)`](/api/csharp/yarn/dialogue._ctor-ivariablestorage-.md)| Initializes a new instance of the [`Dialogue`](/api/csharp/yarn/dialogue.md) class. |
## Methods
|Name|Description|
|:---|:---|
|[`AddProgram(Program)`](/api/csharp/yarn/dialogue.addprogram-program-.md)| Loads the nodes from the specified [`Program`](/api/csharp/yarn/program.md), and adds them to the nodes already loaded. |
|[`Continue()`](/api/csharp/yarn/dialogue.continue.md)| Starts, or continues, execution of the current Program. |
|[`ExpandSubstitutions(String, IList<String>)`](/api/csharp/yarn/dialogue.expandsubstitutions-system.string,system.collections.generic.ilist-system.string--.md)| Replaces all substitution markers in a text with the given substitution list. |
|[`GetStringIDForNode(String)`](/api/csharp/yarn/dialogue.getstringidfornode-system.string-.md)| Returns the string ID that contains the original, uncompiled source text for a node. |
|[`GetTagsForNode(String)`](/api/csharp/yarn/dialogue.gettagsfornode-system.string-.md)| Returns the tags for the node 'nodeName'. |
|[`NodeExists(String)`](/api/csharp/yarn/dialogue.nodeexists-system.string-.md)| Gets a value indicating whether a specified node exists in the Program. |
|[`ParseMarkup(String)`](/api/csharp/yarn/dialogue.parsemarkup-system.string-.md)| Parses a line of text, and produces a [`MarkupParseResult`](/api/csharp/yarn.markup/markupparseresult.md) containing the results. |
|[`SetNode(String)`](/api/csharp/yarn/dialogue.setnode-system.string-.md)| Prepares the [`Dialogue`](/api/csharp/yarn/dialogue.md) that the user intends to start running a node. |
|[`SetProgram(Program)`](/api/csharp/yarn/dialogue.setprogram-program-.md)| Loads all nodes from the provided [`Program`](/api/csharp/yarn/program.md). |
|[`SetSelectedOption(Int32)`](/api/csharp/yarn/dialogue.setselectedoption-system.int32-.md)| Signals to the [`Dialogue`](/api/csharp/yarn/dialogue.md) that the user has selected a specified [`OptionSet.Option`](/api/csharp/yarn/optionset.option.md). |
|[`Stop()`](/api/csharp/yarn/dialogue.stop.md)| Immediately stops the [`Dialogue`](/api/csharp/yarn/dialogue.md). |
|[`UnloadAll()`](/api/csharp/yarn/dialogue.unloadall.md)| Unloads all nodes from the Dialogue. |
## Properties
|Name|Description|
|:---|:---|
|[`CommandHandler`](/api/csharp/yarn/dialogue.commandhandler.md)| Gets or sets the [`CommandHandler`](/api/csharp/yarn/commandhandler.md) that is called when a command is to be delivered to the game. |
|[`CurrentNode`](/api/csharp/yarn/dialogue.currentnode.md)| Gets the name of the node that this Dialogue is currently executing. |
|[`DialogueCompleteHandler`](/api/csharp/yarn/dialogue.dialoguecompletehandler.md)| Gets or sets the [`DialogueCompleteHandler`](/api/csharp/yarn/dialoguecompletehandler.md) that is called when the dialogue reaches its end. |
|[`IsActive`](/api/csharp/yarn/dialogue.isactive.md)| Gets a value indicating whether the Dialogue is currently executing Yarn instructions. |
|[`LanguageCode`](/api/csharp/yarn/dialogue.languagecode.md)| Gets or sets the [`Dialogue`](/api/csharp/yarn/dialogue.md)'s locale, as an IETF BCP 47 code. |
|[`Library`](/api/csharp/yarn/dialogue.library.md)| Gets the [`Library`](/api/csharp/yarn/library.md) that this Dialogue uses to locate functions. |
|[`LineHandler`](/api/csharp/yarn/dialogue.linehandler.md)| Gets or sets the [`LineHandler`](/api/csharp/yarn/linehandler.md) that is called when a line is ready to be shown to the user. |
|[`LogDebugMessage`](/api/csharp/yarn/dialogue.logdebugmessage.md)| Invoked when the Dialogue needs to report debugging information. |
|[`LogErrorMessage`](/api/csharp/yarn/dialogue.logerrormessage.md)| Invoked when the Dialogue needs to report an error. |
|[`NodeCompleteHandler`](/api/csharp/yarn/dialogue.nodecompletehandler.md)| Gets or sets the [`NodeCompleteHandler`](/api/csharp/yarn/nodecompletehandler.md) that is called when a node is complete. |
|[`NodeNames`](/api/csharp/yarn/dialogue.nodenames.md)| Gets the names of the nodes in the currently loaded Program. |
|[`NodeStartHandler`](/api/csharp/yarn/dialogue.nodestarthandler.md)| Gets or sets the [`NodeStartHandler`](/api/csharp/yarn/nodestarthandler.md) that is called when a node is started. |
|[`OptionsHandler`](/api/csharp/yarn/dialogue.optionshandler.md)| Gets or sets the [`OptionsHandler`](/api/csharp/yarn/optionshandler.md) that is called when a set of options are ready to be shown to the user. |
|[`PrepareForLinesHandler`](/api/csharp/yarn/dialogue.prepareforlineshandler.md)| Gets or sets the [`PrepareForLinesHandler`](/api/csharp/yarn/dialogue.prepareforlineshandler.md) that is called when the dialogue anticipates delivering some lines. |
## Fields
|Name|Description|
|:---|:---|
|[`DefaultStartNodeName`](/api/csharp/yarn/dialogue.defaultstartnodename.md)|The node that execution will start from.|
## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L391), line 391.
