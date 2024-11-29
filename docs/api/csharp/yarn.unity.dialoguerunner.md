# DialogueRunner

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary



```csharp
public class DialogueRunner : MonoBehaviour
```

## Fields

|Name|Description|
|:---|:---|
|[autoStart](/docs/api/csharp/yarn.unity.dialoguerunner.autostart.md)||
|[onCommand](/docs/api/csharp/yarn.unity.dialoguerunner.oncommand.md)|A  <code>StringUnityEvent</code>  that is called when a  <a href="yarn.command.md">Command</a>  is received.|
|[onDialogueComplete](/docs/api/csharp/yarn.unity.dialoguerunner.ondialoguecomplete.md)|A Unity event that is called once the dialogue has completed.|
|[onDialogueStart](/docs/api/csharp/yarn.unity.dialoguerunner.ondialoguestart.md)|A Unity event that is called when the dialogue starts running.|
|[onNodeComplete](/docs/api/csharp/yarn.unity.dialoguerunner.onnodecomplete.md)|A Unity event that is called when a node is complete.|
|[onNodeStart](/docs/api/csharp/yarn.unity.dialoguerunner.onnodestart.md)|A Unity event that is called when a node starts running.|
|[runSelectedOptionAsLine](/docs/api/csharp/yarn.unity.dialoguerunner.runselectedoptionasline.md)||
|[startNode](/docs/api/csharp/yarn.unity.dialoguerunner.startnode.md)||

## Methods

|Name|Description|
|:---|:---|
|[AddCommandHandler(string,Delegate)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-1.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,MethodInfo)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-2.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddFunction(string,Delegate)](/docs/api/csharp/yarn.unity.dialoguerunner.addfunction.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[Awake()](/docs/api/csharp/yarn.unity.dialoguerunner.awake.md)||
|[CancelCurrentLine()](/docs/api/csharp/yarn.unity.dialoguerunner.cancelcurrentline.md)||
|[HurryUpCurrentLine()](/docs/api/csharp/yarn.unity.dialoguerunner.hurryupcurrentline.md)||
|[LoadStateFromPersistentStorage(string)](/docs/api/csharp/yarn.unity.dialoguerunner.loadstatefrompersistentstorage.md)|Loads all variables from the requested file in persistent storage into the Dialogue Runner's variable storage.|
|[LoadStateFromPlayerPrefs(string)](/docs/api/csharp/yarn.unity.dialoguerunner.loadstatefromplayerprefs.md)|Loads all variables from the  <code>UnityEngine.PlayerPrefs</code>  object into the Dialogue Runner's variable storage.|
|[OnDestroy()](/docs/api/csharp/yarn.unity.dialoguerunner.ondestroy.md)||
|[RemoveCommandHandler(string)](/docs/api/csharp/yarn.unity.dialoguerunner.removecommandhandler.md)|Removes a command handler.|
|[RemoveFunction(string)](/docs/api/csharp/yarn.unity.dialoguerunner.removefunction.md)|Remove a registered function.|
|[SaveStateToPersistentStorage(string)](/docs/api/csharp/yarn.unity.dialoguerunner.savestatetopersistentstorage.md)|Saves all variables from variable storage into the persistent storage.|
|[SaveStateToPlayerPrefs(string)](/docs/api/csharp/yarn.unity.dialoguerunner.savestatetoplayerprefs.md)|Saves all variables in the Dialogue Runner's variable storage into the  <code>UnityEngine.PlayerPrefs</code>  object.|
|[SetProject(YarnProject)](/docs/api/csharp/yarn.unity.dialoguerunner.setproject.md)|Sets the dialogue runner's Yarn Project.|
|[SplitCommandText(string)](/docs/api/csharp/yarn.unity.dialoguerunner.splitcommandtext.md)|Splits input into a number of non-empty sub-strings, separated by whitespace, and grouping double-quoted strings into a single sub-string.|
|[Start()](/docs/api/csharp/yarn.unity.dialoguerunner.start.md)||
|[StartDialogue(string)](/docs/api/csharp/yarn.unity.dialoguerunner.startdialogue.md)||
|[Stop()](/docs/api/csharp/yarn.unity.dialoguerunner.stop.md)||

## Properties

|Name|Description|
|:---|:---|
|[Dialogue](/docs/api/csharp/yarn.unity.dialoguerunner.dialogue.md)||
|[DialogueTask](/docs/api/csharp/yarn.unity.dialoguerunner.dialoguetask.md)|Gets a  <code>System.Threading.Tasks.Task</code>  that completes when the dialogue runner finishes its dialogue.|
|[DialogueViews](/docs/api/csharp/yarn.unity.dialoguerunner.dialogueviews.md)||
|[IsDialogueRunning](/docs/api/csharp/yarn.unity.dialoguerunner.isdialoguerunning.md)|Gets a value that indicates if the dialogue is actively running.|
|[LineProvider](/docs/api/csharp/yarn.unity.dialoguerunner.lineprovider.md)||
|[VariableStorage](/docs/api/csharp/yarn.unity.dialoguerunner.variablestorage.md)||
|[YarnProject](/docs/api/csharp/yarn.unity.dialoguerunner.yarnproject.md)||

