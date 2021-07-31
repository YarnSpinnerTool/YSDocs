# DialogueRunner

The \[DialogueRunner\]\(\) component acts as the interface between your game and Yarn Spinner.

```csharp
public class DialogueRunner : MonoBehaviour
```

## Methods

| Name | Description |
| :--- | :--- |
| [`Add(YarnProgram, String, IEnumerable<StringTableEntry>)`](dialoguerunner.add-yarnprogram-system.string-ienumerable-stringtableentry.md) |  |
| [`AddCommandHandler(String, System.Action)`](dialoguerunner.addcommandhandler-system.string-system.action.md) |  |
| [`AddCommandHandler(String, System.Func<Coroutine>)`](dialoguerunner.addcommandhandler-system.string-system.func-coroutine.md) |  |
| [`AddCommandHandler<T1>(String, System.Action<T1>)`](dialoguerunner.addcommandhandler-1-system.string-system.action-0.md) |  |
| [`AddCommandHandler<T1>(String, System.Func<T1, Coroutine>)`](dialoguerunner.addcommandhandler-1-system.string-system.func-0-coroutine.md) |  |
| [`AddCommandHandler<T1, T2>(String, System.Action<T1, T2>)`](dialoguerunner.addcommandhandler-2-system.string-system.action-0-1.md) |  |
| [`AddCommandHandler<T1, T2>(String, System.Func<T1, T2, Coroutine>)`](dialoguerunner.addcommandhandler-2-system.string-system.func-0-1-coroutine.md) |  |
| [`AddCommandHandler<T1, T2, T3>(String, System.Action<T1, T2, T3>)`](dialoguerunner.addcommandhandler-3-system.string-system.action-0-1-2.md) |  |
| [`AddCommandHandler<T1, T2, T3>(String, System.Func<T1, T2, T3, Coroutine>)`](dialoguerunner.addcommandhandler-3-system.string-system.func-0-1-2-coroutine.md) |  |
| [`AddCommandHandler<T1, T2, T3, T4>(String, System.Action<T1, T2, T3, T4>)`](dialoguerunner.addcommandhandler-4-system.string-system.action-0-1-2-3.md) |  |
| [`AddCommandHandler<T1, T2, T3, T4>(String, System.Func<T1, T2, T3, T4, Coroutine>)`](dialoguerunner.addcommandhandler-4-system.string-system.func-0-1-2-3-coroutine.md) |  |
| [`AddCommandHandler<T1, T2, T3, T4, T5>(String, System.Action<T1, T2, T3, T4, T5>)`](dialoguerunner.addcommandhandler-5-system.string-system.action-0-1-2-3-4.md) |  |
| [`AddCommandHandler<T1, T2, T3, T4, T5>(String, System.Func<T1, T2, T3, T4, T5, Coroutine>)`](dialoguerunner.addcommandhandler-5-system.string-system.func-0-1-2-3-4-coroutine.md) |  |
| [`AddCommandHandler<T1, T2, T3, T4, T5, T6>(String, System.Action<T1, T2, T3, T4, T5, T6>)`](dialoguerunner.addcommandhandler-6-system.string-system.action-0-1-2-3-4-5.md) |  |
| [`AddCommandHandler<T1, T2, T3, T4, T5, T6>(String, System.Func<T1, T2, T3, T4, T5, T6, Coroutine>)`](dialoguerunner.addcommandhandler-6-system.string-system.func-0-1-2-3-4-5-coroutine.md) |  |
| [`AddFunction<TResult>(String, System.Func<TResult>)`](dialoguerunner.addfunction-1-system.string-system.func-0.md) |  |
| [`AddFunction<TResult, T1>(String, System.Func<TResult, T1>)`](dialoguerunner.addfunction-2-system.string-system.func-0-1.md) |  |
| [`AddFunction<TResult, T1, T2>(String, System.Func<TResult, T1, T2>)`](dialoguerunner.addfunction-3-system.string-system.func-0-1-2.md) |  |
| [`AddFunction<TResult, T1, T2, T3>(String, System.Func<TResult, T1, T2, T3>)`](dialoguerunner.addfunction-4-system.string-system.func-0-1-2-3.md) |  |
| [`AddFunction<TResult, T1, T2, T3, T4>(String, System.Func<TResult, T1, T2, T3, T4>)`](dialoguerunner.addfunction-5-system.string-system.func-0-1-2-3-4.md) |  |
| [`AddFunction<TResult, T1, T2, T3, T4, T5>(String, System.Func<TResult, T1, T2, T3, T4, T5>)`](dialoguerunner.addfunction-6-system.string-system.func-0-1-2-3-4-5.md) |  |
| [`AddFunction<TResult, T1, T2, T3, T4, T5, T6>(String, System.Func<TResult, T1, T2, T3, T4, T5, T6>)`](dialoguerunner.addfunction-7-system.string-system.func-0-1-2-3-4-5-6.md) |  |
| [`Clear()`](dialoguerunner.clear.md) | Unloads all nodes from the `Yarn.Unity.DialogueRunner.dialogue`. |
| [`GetTagsForNode(String)`](dialoguerunner.gettagsfornode-string.md) | Returns the collection of tags that the node associated with the node named `nodeName`. |
| [`NodeExists(String)`](dialoguerunner.nodeexists-system.string.md) | Returns `true` when a node named `nodeName` has been loaded. |
| [`OnViewUserIntentNextLine()`](dialoguerunner.onviewuserintentnextline.md) | Called by a [`DialogueViewBase`](../dialogueviewbase/) derived class from [`dialogueViews`](dialoguerunner.dialogueviews.md) to inform the [`DialogueRunner`](./) that the user intents to proceed to the next line. |
| [`RemoveCommandHandler(String)`](dialoguerunner.removecommandhandler-system.string.md) | Removes a command handler. |
| [`RemoveFunction(String)`](dialoguerunner.removefunction-system.string.md) | Remove a registered function. |
| [`ResetDialogue()`](dialoguerunner.resetdialogue.md) | Starts running the dialogue again from the node named [`startNode`](dialoguerunner.startnode.md). |
| [`StartDialogue()`](dialoguerunner.startdialogue.md) | Starts running dialogue. The node specified by [`startNode`](dialoguerunner.startnode.md) will start running. |
| [`StartDialogue(String)`](dialoguerunner.startdialogue-system.string.md) | Start the dialogue from a specific node. |
| [`Stop()`](dialoguerunner.stop.md) | Stops the `Yarn.Unity.DialogueRunner.dialogue`. |

## Fields

| Name | Description |
| :--- | :--- |
| [`continueNextLineOnLineFinished`](dialoguerunner.continuenextlineonlinefinished.md) | Whether the DialogueRunner should automatically proceed to the next line once a line has been finished. |
| [`dialogueViews`](dialoguerunner.dialogueviews.md) | The View classes that will present the dialogue to the user. |
| [`lineProvider`](dialoguerunner.lineprovider.md) |  |
| [`onCommand`](dialoguerunner.oncommand.md) | A [`DialogueRunner.StringUnityEvent`](../dialoguerunner.stringunityevent.md) that is called when a   is received. |
| [`onDialogueComplete`](dialoguerunner.ondialoguecomplete.md) | A Unity event that is called once the dialogue has completed. |
| [`onNodeComplete`](dialoguerunner.onnodecomplete.md) | A Unity event that is called when a node is complete. |
| [`onNodeStart`](dialoguerunner.onnodestart.md) | A Unity event that is called when a node starts running. |
| [`runSelectedOptionAsLine`](dialoguerunner.runselectedoptionasline.md) | If true, when an option is selected, it's as though it were a line. |
| [`startAutomatically`](dialoguerunner.startautomatically.md) | Whether the DialogueRunner should automatically start running dialogue after the scene loads. |
| [`startNode`](dialoguerunner.startnode.md) | The name of the node to start from. |
| [`variableStorage`](dialoguerunner.variablestorage.md) | The variable storage object. |
| [`yarnProgram`](dialoguerunner.yarnprogram.md) | The [`YarnProgram`](../yarnprogram/) assets that should be loaded on scene start. |

## Properties

| Name | Description |
| :--- | :--- |
| [`CurrentNodeName`](dialoguerunner.currentnodename.md) | Gets the name of the current node that is being run. |
| [`Dialogue`](dialoguerunner.dialogue.md) | Gets the underlying [`Dialogue`](dialoguerunner.dialogue.md) object that runs the Yarn code. |
| [`IsDialogueRunning`](dialoguerunner.isdialoguerunning.md) | Gets a value that indicates if the dialogue is actively running. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L43), line 43.

