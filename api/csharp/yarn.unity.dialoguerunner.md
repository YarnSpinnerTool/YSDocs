# DialogueRunner

Class in [Yarn.Unity](api/csharp/yarn.unity.md)

Inherits from `MonoBehaviour`

## Summary


The DialogueRunner component acts as the interface between your game and
Yarn Spinner.


```csharp
public class DialogueRunner : MonoBehaviour
```

## Classes

|Name|Description|
|:---|:---|
|[StringUnityEvent](api/csharp/yarn.unity.dialoguerunner.stringunityevent.md)|A type of  <code>UnityEvent</code>  that takes a single string parameter.|

## Fields

|Name|Description|
|:---|:---|
|[dialogueViews](api/csharp/yarn.unity.dialoguerunner.dialogueviews.md)|The View classes that will present the dialogue to the user.|
|[lineProvider](api/csharp/yarn.unity.dialoguerunner.lineprovider.md)||
|[onCommand](api/csharp/yarn.unity.dialoguerunner.oncommand.md)|A  <a href="yarn.unity.dialoguerunner.stringunityevent.md">StringUnityEvent</a>  that is called when a  <code>Command</code>  is received.|
|[onDialogueComplete](api/csharp/yarn.unity.dialoguerunner.ondialoguecomplete.md)|A Unity event that is called once the dialogue has completed.|
|[onNodeComplete](api/csharp/yarn.unity.dialoguerunner.onnodecomplete.md)|A Unity event that is called when a node is complete.|
|[onNodeStart](api/csharp/yarn.unity.dialoguerunner.onnodestart.md)|A Unity event that is called when a node starts running.|
|[runSelectedOptionAsLine](api/csharp/yarn.unity.dialoguerunner.runselectedoptionasline.md)|If true, when an option is selected, it's as though it were a line.|
|[startAutomatically](api/csharp/yarn.unity.dialoguerunner.startautomatically.md)|Whether the DialogueRunner should automatically start running dialogue after the scene loads.|
|[startNode](api/csharp/yarn.unity.dialoguerunner.startnode.md)|The name of the node to start from.|
|[verboseLogging](api/csharp/yarn.unity.dialoguerunner.verboselogging.md)|If true, will print Debug.Log messages every time it enters a node, and other frequent events.|
|[yarnProject](api/csharp/yarn.unity.dialoguerunner.yarnproject.md)|The  <a href="yarn.unity.yarnproject.md">YarnProject</a>  asset that should be loaded on scene start.|

## Methods

|Name|Description|
|:---|:---|
|[AddCommandHandler(string,Delegate)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-1.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-9.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<Coroutine>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-2.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-10.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, Coroutine>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-3.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-11.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, Coroutine>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-4.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-12.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, Coroutine>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-5.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-13.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, Coroutine>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-6.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-14.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, Coroutine>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-7.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5, T6>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-15.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, Coroutine>)](api/csharp/yarn.unity.dialoguerunner.addcommandhandler-8.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddFunction(string,Delegate)](api/csharp/yarn.unity.dialoguerunner.addfunction-1.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult>)](api/csharp/yarn.unity.dialoguerunner.addfunction-2.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult, T1>)](api/csharp/yarn.unity.dialoguerunner.addfunction-3.md)||
|[AddFunction(string,System.Func<TResult, T1, T2>)](api/csharp/yarn.unity.dialoguerunner.addfunction-4.md)||
|[AddFunction(string,System.Func<TResult, T1, T2, T3>)](api/csharp/yarn.unity.dialoguerunner.addfunction-5.md)||
|[AddFunction(string,System.Func<TResult, T1, T2, T3, T4>)](api/csharp/yarn.unity.dialoguerunner.addfunction-6.md)||
|[AddFunction(string,System.Func<TResult, T1, T2, T3, T4, T5>)](api/csharp/yarn.unity.dialoguerunner.addfunction-7.md)||
|[AddFunction(string,System.Func<TResult, T1, T2, T3, T4, T5, T6>)](api/csharp/yarn.unity.dialoguerunner.addfunction-8.md)||
|[Clear()](api/csharp/yarn.unity.dialoguerunner.clear.md)|Unloads all nodes from the  <a href="yarn.unity.dialoguerunner.dialogue.md">Dialogue</a> .|
|[GetTagsForNode(String)](api/csharp/yarn.unity.dialoguerunner.gettagsfornode.md)|Returns the collection of tags that the node associated with the node named `nodeName`.|
|[LoadStateFromPlayerPrefs(string)](api/csharp/yarn.unity.dialoguerunner.loadstatefromplayerprefs.md)|Loads all variables from the  <code>PlayerPrefs</code>  object into the Dialogue Runner's variable storage.|
|[NodeExists(string)](api/csharp/yarn.unity.dialoguerunner.nodeexists.md)|Returns `true` when a node named `nodeName` has been loaded.|
|[OnViewRequestedInterrupt()](api/csharp/yarn.unity.dialoguerunner.onviewrequestedinterrupt.md)|Called by a  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  derived class from <a href="yarn.unity.dialoguerunner.dialogueviews.md">dialogueViews</a>  to inform the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  that the user intents to proceed to the next line.|
|[RemoveCommandHandler(string)](api/csharp/yarn.unity.dialoguerunner.removecommandhandler.md)|Removes a command handler.|
|[RemoveFunction(string)](api/csharp/yarn.unity.dialoguerunner.removefunction.md)|Remove a registered function.|
|[ResetDialogue(string)](api/csharp/yarn.unity.dialoguerunner.resetdialogue.md)|Starts running the dialogue again.|
|[SaveStateToPlayerPrefs(string)](api/csharp/yarn.unity.dialoguerunner.savestatetoplayerprefs.md)|Saves all variables in the Dialogue Runner's variable storage into the  <code>PlayerPrefs</code>  object.|
|[SetDialogueViews(DialogueViewBase[])](api/csharp/yarn.unity.dialoguerunner.setdialogueviews.md)|Sets the dialogue views and makes sure the callback  <code>DialogueViewBase.MarkLineComplete</code>  will respond correctly.|
|[SetInitialVariables(bool)](api/csharp/yarn.unity.dialoguerunner.setinitialvariables.md)|Loads any initial variables declared in the program and loads that variable with its default declaration value into the variable storage. Any variable that is already in the storage will be skipped, the assumption is that this means the value has been overridden at some point and shouldn't be otherwise touched. Can force an override of the existing values with the default if that is desired.|
|[SetProject(YarnProject)](api/csharp/yarn.unity.dialoguerunner.setproject.md)|Replaces this DialogueRunner's yarn project with the provided project.|
|[SplitCommandText(string)](api/csharp/yarn.unity.dialoguerunner.splitcommandtext.md)|Splits input into a number of non-empty sub-strings, separated by whitespace, and grouping double-quoted strings into a single sub-string.|
|[StartDialogue(string)](api/csharp/yarn.unity.dialoguerunner.startdialogue.md)|Start the dialogue from a specific node.|
|[Stop()](api/csharp/yarn.unity.dialoguerunner.stop.md)|Stops the  <a href="yarn.unity.dialoguerunner.dialogue.md">Dialogue</a> .|

## Properties

|Name|Description|
|:---|:---|
|[CurrentNodeName](api/csharp/yarn.unity.dialoguerunner.currentnodename.md)|Gets the name of the current node that is being run.|
|[Dialogue](api/csharp/yarn.unity.dialoguerunner.dialogue.md)|Gets the underlying  <a href="yarn.unity.dialoguerunner.dialogue.md">Dialogue</a>  object that runs the Yarn code.|
|[IsDialogueRunning](api/csharp/yarn.unity.dialoguerunner.isdialoguerunning.md)|Gets a value that indicates if the dialogue is actively running.|
|[VariableStorage](api/csharp/yarn.unity.dialoguerunner.variablestorage.md)|The variable storage object.|

