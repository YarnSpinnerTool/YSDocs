# DialogueRunner

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary


The DialogueRunner component acts as the interface between your game and
Yarn Spinner.


```csharp
public class DialogueRunner : MonoBehaviour, IActionRegistration
```

## Classes

|Name|Description|
|:---|:---|
|[StringUnityEvent](/docs/api/csharp/yarn.unity.dialoguerunner.stringunityevent.md)|A type of  <code>UnityEngine.Events.UnityEvent</code>  that takes a single string parameter.|

## Fields

|Name|Description|
|:---|:---|
|[dialogueViews](/docs/api/csharp/yarn.unity.dialoguerunner.dialogueviews.md)|The View classes that will present the dialogue to the user.|
|[lineProvider](/docs/api/csharp/yarn.unity.dialoguerunner.lineprovider.md)||
|[onCommand](/docs/api/csharp/yarn.unity.dialoguerunner.oncommand.md)|A  <a href="yarn.unity.dialoguerunner.stringunityevent.md">StringUnityEvent</a>  that is called when a  <a href="yarn.command.md">Command</a>  is received.|
|[onDialogueComplete](/docs/api/csharp/yarn.unity.dialoguerunner.ondialoguecomplete.md)|A Unity event that is called once the dialogue has completed.|
|[onDialogueStart](/docs/api/csharp/yarn.unity.dialoguerunner.ondialoguestart.md)|A Unity event that is called when the dialogue starts running.|
|[onNodeComplete](/docs/api/csharp/yarn.unity.dialoguerunner.onnodecomplete.md)|A Unity event that is called when a node is complete.|
|[onNodeStart](/docs/api/csharp/yarn.unity.dialoguerunner.onnodestart.md)|A Unity event that is called when a node starts running.|
|[runSelectedOptionAsLine](/docs/api/csharp/yarn.unity.dialoguerunner.runselectedoptionasline.md)|If true, when an option is selected, it's as though it were a line.|
|[startAutomatically](/docs/api/csharp/yarn.unity.dialoguerunner.startautomatically.md)|Whether the DialogueRunner should automatically start running dialogue after the scene loads.|
|[startNode](/docs/api/csharp/yarn.unity.dialoguerunner.startnode.md)|The name of the node to start from.|
|[verboseLogging](/docs/api/csharp/yarn.unity.dialoguerunner.verboselogging.md)|If true, will print Debug.Log messages every time it enters a node, and other frequent events.|
|[yarnProject](/docs/api/csharp/yarn.unity.dialoguerunner.yarnproject.md)|The  <a href="yarn.unity.yarnproject.md">YarnProject</a>  asset that should be loaded on scene start.|

## Methods

|Name|Description|
|:---|:---|
|[AddCommandHandler(string,System.Action)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-25.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,Delegate)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-1.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-14.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-3.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,MethodInfo)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-2.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-26.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-15.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-4.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-35.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-24.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-13.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-27.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-16.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-5.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-28.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-17.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-6.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-29.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-18.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-7.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-30.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-19.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-8.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5, T6>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-31.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-20.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-9.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5, T6, T7>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-32.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-21.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-10.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5, T6, T7, T8>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-33.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-22.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-11.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5, T6, T7, T8, T9>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-34.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, IEnumerator>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-23.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, Coroutine>)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-12.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddFunction(string,Delegate)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-1.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-2.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-11.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-12.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-3.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-4.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, T3, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-5.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, T3, T4, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-6.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, T3, T4, T5, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-7.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, T3, T4, T5, T6, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-8.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, T3, T4, T5, T6, T7, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-9.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, TResult>)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction-10.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[Clear()](/docs/api/csharp/yarn.unity.dialoguerunner.clear.md)|Unloads all nodes from the  <a href="yarn.unity.dialoguerunner.dialogue.md">Dialogue</a> .|
|[GetTagsForNode(String)](/docs/api/csharp/yarn.unity.dialoguerunner.gettagsfornode.md)|Returns the collection of tags that the node associated with the node named `nodeName`.|
|[LoadStateFromPersistentStorage(string)](/docs/api/csharp/yarn.unity.dialoguerunner.loadstatefrompersistentstorage.md)|Loads all variables from the requested file in persistent storage into the Dialogue Runner's variable storage.|
|[LoadStateFromPlayerPrefs(string)](/docs/api/csharp/yarn.unity.dialoguerunner.loadstatefromplayerprefs.md)|Loads all variables from the  <code>UnityEngine.PlayerPrefs</code>  object into the Dialogue Runner's variable storage.|
|[NodeExists(string)](/docs/api/csharp/yarn.unity.dialoguerunner.nodeexists.md)|Returns `true` when a node named `nodeName` has been loaded.|
|[OnViewRequestedInterrupt()](/docs/api/csharp/yarn.unity.dialoguerunner.onviewrequestedinterrupt.md)|Called by a  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  derived class from <a href="yarn.unity.dialoguerunner.dialogueviews.md">dialogueViews</a>  to inform the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  that the user intents to proceed to the next line.|
|[RemoveCommandHandler(string)](/docs/api/csharp/yarn.unity.dialoguerunner.removecommandhandler.md)|Removes a command handler.|
|[RemoveFunction(string)](/docs/api/csharp/yarn.unity.dialoguerunner.removefunction.md)|Remove a registered function.|
|[ResetDialogue(string)](/docs/api/csharp/yarn.unity.dialoguerunner.resetdialogue.md)|Starts running the dialogue again.|
|[SaveStateToPersistentStorage(string)](/docs/api/csharp/yarn.unity.dialoguerunner.savestatetopersistentstorage.md)|Saves all variables from variable storage into the persistent storage.|
|[SaveStateToPlayerPrefs(string)](/docs/api/csharp/yarn.unity.dialoguerunner.savestatetoplayerprefs.md)|Saves all variables in the Dialogue Runner's variable storage into the  <code>UnityEngine.PlayerPrefs</code>  object.|
|[SetDialogueViews(DialogueViewBase[])](/docs/api/csharp/yarn.unity.dialoguerunner.setdialogueviews.md)|Sets the dialogue views and makes sure the callback  <code>DialogueViewBase.MarkLineComplete</code>  will respond correctly.|
|[SetInitialVariables(bool)](/docs/api/csharp/yarn.unity.dialoguerunner.setinitialvariables.md)|Loads any initial variables declared in the program and loads that variable with its default declaration value into the variable storage. Any variable that is already in the storage will be skipped, the assumption is that this means the value has been overridden at some point and shouldn't be otherwise touched. Can force an override of the existing values with the default if that is desired.|
|[SetProject(YarnProject)](/docs/api/csharp/yarn.unity.dialoguerunner.setproject.md)|Replaces this DialogueRunner's yarn project with the provided project.|
|[SplitCommandText(string)](/docs/api/csharp/yarn.unity.dialoguerunner.splitcommandtext.md)|Splits input into a number of non-empty sub-strings, separated by whitespace, and grouping double-quoted strings into a single sub-string.|
|[StartDialogue(string)](/docs/api/csharp/yarn.unity.dialoguerunner.startdialogue.md)|Start the dialogue from a specific node.|
|[Stop()](/docs/api/csharp/yarn.unity.dialoguerunner.stop.md)|Stops the  <a href="yarn.unity.dialoguerunner.dialogue.md">Dialogue</a> .|

## Properties

|Name|Description|
|:---|:---|
|[CurrentNodeName](/docs/api/csharp/yarn.unity.dialoguerunner.currentnodename.md)|Gets the name of the current node that is being run.|
|[Dialogue](/docs/api/csharp/yarn.unity.dialoguerunner.dialogue.md)|Gets the underlying  <a href="yarn.unity.dialoguerunner.dialogue.md">Dialogue</a>  object that runs the Yarn code.|
|[IsDialogueRunning](/docs/api/csharp/yarn.unity.dialoguerunner.isdialoguerunning.md)|Gets a value that indicates if the dialogue is actively running.|
|[VariableStorage](/docs/api/csharp/yarn.unity.dialoguerunner.variablestorage.md)|The variable storage object.|

