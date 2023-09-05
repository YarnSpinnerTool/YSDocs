# Dialogue

Class in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


Co-ordinates the execution of Yarn programs.


```csharp
public class Dialogue : IAttributeMarkerProcessor
```

## Constructors

|Name|Description|
|:---|:---|
|[Dialogue(Yarn.IVariableStorage)](/docs/api/csharp/yarn.dialogue..ctor.md)|Initializes a new instance of the  <a href="yarn.dialogue.md">Dialogue</a>  class.|

## Fields

|Name|Description|
|:---|:---|
|[DefaultStartNodeName](/docs/api/csharp/yarn.dialogue.defaultstartnodename.md)|The node that execution will start from.|

## Methods

|Name|Description|
|:---|:---|
|[AddProgram(Program)](/docs/api/csharp/yarn.dialogue.addprogram.md)|Loads the nodes from the specified  <a href="yarn.program.md">Program</a> , and adds them to the nodes already loaded.|
|[Continue()](/docs/api/csharp/yarn.dialogue.continue.md)|Starts, or continues, execution of the current Program.|
|[ExpandSubstitutions(string,IList<string>)](/docs/api/csharp/yarn.dialogue.expandsubstitutions.md)|Replaces all substitution markers in a text with the given substitution list.|
|[GetStringIDForNode(string)](/docs/api/csharp/yarn.dialogue.getstringidfornode.md)|Returns the string ID that contains the original, uncompiled source text for a node.|
|[GetTagsForNode(string)](/docs/api/csharp/yarn.dialogue.gettagsfornode.md)|Returns the tags for the node  <code>nodeName</code> .|
|[NodeExists(string)](/docs/api/csharp/yarn.dialogue.nodeexists.md)|Gets a value indicating whether a specified node exists in the Program.|
|[ParseMarkup(string)](/docs/api/csharp/yarn.dialogue.parsemarkup.md)|Parses a line of text, and produces a  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  containing the results.|
|[SetNode(string)](/docs/api/csharp/yarn.dialogue.setnode.md)|Prepares the  <a href="yarn.dialogue.md">Dialogue</a>  that the user intends to start running a node.|
|[SetProgram(Program)](/docs/api/csharp/yarn.dialogue.setprogram.md)|Loads all nodes from the provided  <a href="yarn.program.md">Program</a> .|
|[SetSelectedOption(int)](/docs/api/csharp/yarn.dialogue.setselectedoption.md)|Signals to the  <a href="yarn.dialogue.md">Dialogue</a>  that the user has selected a specified  <a href="yarn.optionset.option.md">Option</a> .|
|[Stop()](/docs/api/csharp/yarn.dialogue.stop.md)|Immediately stops the  <a href="yarn.dialogue.md">Dialogue</a> .|
|[UnloadAll()](/docs/api/csharp/yarn.dialogue.unloadall.md)|Unloads all nodes from the Dialogue.|

## Properties

|Name|Description|
|:---|:---|
|[CommandHandler](/docs/api/csharp/yarn.dialogue.commandhandler.md)|Gets or sets the  <a href="yarn.commandhandler.md">CommandHandler</a>  that is called when a command is to be delivered to the game.|
|[CurrentNode](/docs/api/csharp/yarn.dialogue.currentnode.md)|Gets the name of the node that this Dialogue is currently executing.|
|[DialogueCompleteHandler](/docs/api/csharp/yarn.dialogue.dialoguecompletehandler.md)|Gets or sets the  <a href="yarn.dialoguecompletehandler.md">DialogueCompleteHandler</a>  that is called when the dialogue reaches its end.|
|[IsActive](/docs/api/csharp/yarn.dialogue.isactive.md)|Gets a value indicating whether the Dialogue is currently executing Yarn instructions.|
|[LanguageCode](/docs/api/csharp/yarn.dialogue.languagecode.md)|Gets or sets the  <a href="yarn.dialogue.md">Dialogue</a> 's locale, as an IETF BCP 47 code.|
|[Library](/docs/api/csharp/yarn.dialogue.library.md)|Gets the  <a href="yarn.library.md">Library</a>  that this Dialogue uses to locate functions.|
|[LineHandler](/docs/api/csharp/yarn.dialogue.linehandler.md)|Gets or sets the  <a href="yarn.linehandler.md">LineHandler</a>  that is called when a line is ready to be shown to the user.|
|[LogDebugMessage](/docs/api/csharp/yarn.dialogue.logdebugmessage.md)|Invoked when the Dialogue needs to report debugging information.|
|[LogErrorMessage](/docs/api/csharp/yarn.dialogue.logerrormessage.md)|Invoked when the Dialogue needs to report an error.|
|[NodeCompleteHandler](/docs/api/csharp/yarn.dialogue.nodecompletehandler.md)|Gets or sets the  <a href="yarn.nodecompletehandler.md">NodeCompleteHandler</a>  that is called when a node is complete.|
|[NodeNames](/docs/api/csharp/yarn.dialogue.nodenames.md)|Gets the names of the nodes in the currently loaded Program.|
|[NodeStartHandler](/docs/api/csharp/yarn.dialogue.nodestarthandler.md)|Gets or sets the  <a href="yarn.nodestarthandler.md">NodeStartHandler</a>  that is called when a node is started.|
|[OptionsHandler](/docs/api/csharp/yarn.dialogue.optionshandler.md)|Gets or sets the  <a href="yarn.optionshandler.md">OptionsHandler</a>  that is called when a set of options are ready to be shown to the user.|
|[PrepareForLinesHandler](/docs/api/csharp/yarn.dialogue.prepareforlineshandler.md)|Gets or sets the  <a href="yarn.dialogue.prepareforlineshandler.md">PrepareForLinesHandler</a>  that is called when the dialogue anticipates delivering some lines.|
|[VariableStorage](/docs/api/csharp/yarn.dialogue.variablestorage.md)|Gets or sets the object that provides access to storing and retrieving the values of variables.|

