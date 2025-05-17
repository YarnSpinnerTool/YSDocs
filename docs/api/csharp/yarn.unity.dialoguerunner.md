# DialogueRunner

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary



```csharp
public class DialogueRunner : IActionRegistration
```

## Fields

|Name|Description|
|:---|:---|
|[autoStart](/docs/api/csharp/yarn.unity.dialoguerunner.autostart.md)|Whether the dialogue runner will immediately start running dialogue after loading.|
|[onDialogueComplete](/docs/api/csharp/yarn.unity.dialoguerunner.ondialoguecomplete.md)|A Unity event that is called once the dialogue has completed.|
|[onDialogueStart](/docs/api/csharp/yarn.unity.dialoguerunner.ondialoguestart.md)|A Unity event that is called when the dialogue starts running.|
|[onNodeComplete](/docs/api/csharp/yarn.unity.dialoguerunner.onnodecomplete.md)|A Unity event that is called when a node is complete.|
|[onNodeStart](/docs/api/csharp/yarn.unity.dialoguerunner.onnodestart.md)|A Unity event that is called when a node starts running.|
|[onUnhandledCommand](/docs/api/csharp/yarn.unity.dialoguerunner.onunhandledcommand.md)|A  [Command](yarn.unity.unityeventstring.md">UnityEventString</a>  that is called when a  <a href="yarn.command.md)  is received and no command handler was able to handle it.|
|[runSelectedOptionAsLine](/docs/api/csharp/yarn.unity.dialoguerunner.runselectedoptionasline.md)|If this value is set, when an option is selected, the line contained in it ( [Line](yarn.optionset.option.line.md) ) will be delivered to the dialogue runner's dialogue views as though it had been written as a separate line.|
|[startNode](/docs/api/csharp/yarn.unity.dialoguerunner.startnode.md)|The name of the node that will start running immediately after loading.|

## Methods

|Name|Description|
|:---|:---|
|[AddCommandHandler(string,Delegate)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-1.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,MethodInfo)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-2.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddFunction(string,Delegate)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[GetPauseDurationsInsideLine(Markup.MarkupParseResult)](/docs/api/csharp/yarn.unity.dialoguerunner.getpausedurationsinsideline.md)|Creates a stack of typewriter pauses to use to temporarily halt the typewriter effect.|
|[LoadStateFromPersistentStorage(string)](/docs/api/csharp/yarn.unity.dialoguerunner.loadstatefrompersistentstorage.md)|Loads all variables from the requested file in persistent storage into the Dialogue Runner's variable storage.|
|[RegisterFunctionDeclaration(string,Type,Type[])](/docs/api/csharp/yarn.unity.dialoguerunner.registerfunctiondeclaration.md)||
|[RemoveCommandHandler(string)](/docs/api/csharp/yarn.unity.dialoguerunner.removecommandhandler.md)|Removes a command handler.|
|[RemoveFunction(string)](/docs/api/csharp/yarn.unity.dialoguerunner.removefunction.md)|Remove a registered function.|
|[RequestHurryUpLine()](/docs/api/csharp/yarn.unity.dialoguerunner.requesthurryupline.md)|Requests that all dialogue views speed up their delivery of the current line.|
|[RequestNextLine()](/docs/api/csharp/yarn.unity.dialoguerunner.requestnextline.md)|Requests that all dialogue views stop showing the current line, and prepare to show the next piece of content.|
|[SaveStateToPersistentStorage(string)](/docs/api/csharp/yarn.unity.dialoguerunner.savestatetopersistentstorage.md)|Saves all variables from variable storage into the persistent storage.|
|[SetProject(YarnProject)](/docs/api/csharp/yarn.unity.dialoguerunner.setproject.md)|Sets the dialogue runner's Yarn Project.|
|[SplitCommandText(string)](/docs/api/csharp/yarn.unity.dialoguerunner.splitcommandtext.md)|Splits input into a number of non-empty sub-strings, separated by whitespace, and grouping double-quoted strings into a single sub-string.|
|[StartDialogue(string)](/docs/api/csharp/yarn.unity.dialoguerunner.startdialogue.md)|Starts running a node of dialogue.|
|[Stop()](/docs/api/csharp/yarn.unity.dialoguerunner.stop.md)|Stops the dialogue immediately, and cancels any currently running dialogue views.|

## Properties

|Name|Description|
|:---|:---|
|[Dialogue](/docs/api/csharp/yarn.unity.dialoguerunner.dialogue.md)|Gets the internal  [Dialogue](yarn.unity.dialoguerunner.dialogue.md)  object that reads and executes the Yarn script.|
|[DialoguePresenters](/docs/api/csharp/yarn.unity.dialoguerunner.dialoguepresenters.md)|Gets or sets the collection of dialogue presenters attached to this dialogue runner.|
|[DialogueTask](/docs/api/csharp/yarn.unity.dialoguerunner.dialoguetask.md)|Gets a  [YarnTask](yarn.unity.yarntask-1.md)  that completes when the dialogue runner finishes its dialogue.|
|[DialogueViews](/docs/api/csharp/yarn.unity.dialoguerunner.dialogueviews.md)|Gets or sets the collection of dialogue presenters attached to this dialogue runner.|
|[IsDialogueRunning](/docs/api/csharp/yarn.unity.dialoguerunner.isdialoguerunning.md)|Gets a value that indicates if the dialogue is actively running.|
|[IsInPlaymode](/docs/api/csharp/yarn.unity.dialoguerunner.isinplaymode.md)||
|[LineProvider](/docs/api/csharp/yarn.unity.dialoguerunner.lineprovider.md)|Gets the  [ILineProvider](yarn.unity.ilineprovider.md)  that this dialogue runner uses to fetch localized line content.|
|[NoOptionSelected](/docs/api/csharp/yarn.unity.dialoguerunner.nooptionselected.md)||
|[VariableStorage](/docs/api/csharp/yarn.unity.dialoguerunner.variablestorage.md)|Gets the VariableStorage that this dialogue runner uses to store and access Yarn variables.|
|[YarnProject](/docs/api/csharp/yarn.unity.dialoguerunner.yarnproject.md)|Gets the  [YarnProject](yarn.unity.dialoguerunner.yarnproject.md)  asset that this dialogue runner uses.|

