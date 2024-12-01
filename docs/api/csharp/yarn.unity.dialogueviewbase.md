# DialogueViewBase

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)

{% hint style="warning" %}
This class is <b>obsolete</b> and may be removed from a future version of Yarn Spinner: Use AsyncDialogueViewBase.
{% endhint %}

## Summary


Implements the Yarn Spinner 2 callback-based API for dialogue views
using Yarn Spinner 3.


```csharp
public abstract class DialogueViewBase : AsyncDialogueViewBase
```

## Remarks


You should not use this class in new code. It exists to provide a
compatibility layer for existing Yarn Spinner dialogue views. New
dialogue views should subclass  <a href="yarn.unity.asyncdialogueviewbase.md">AsyncDialogueViewBase</a> 
directly.


## Fields

|Name|Description|
|:---|:---|
|[requestInterrupt](/docs/api/csharp/yarn.unity.dialogueviewbase.requestinterrupt.md)|Represents the method that should be called when this view wants the line to be interrupted.|

## Methods

|Name|Description|
|:---|:---|
|[DialogueComplete()](/docs/api/csharp/yarn.unity.dialogueviewbase.dialoguecomplete.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[DialogueStarted()](/docs/api/csharp/yarn.unity.dialogueviewbase.dialoguestarted.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that dialogue has started.|
|[DismissLine(Action)](/docs/api/csharp/yarn.unity.dialogueviewbase.dismissline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.|
|[InterruptLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.dialogueviewbase.interruptline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.dialogueviewbase.ondialoguecompleteasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.dialogueviewbase.ondialoguestartedasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that dialogue has started.|
|[RunLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.dialogueviewbase.runline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.dialogueviewbase.runlineasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.|
|[RunOptions(DialogueOption[],Action<int>)](/docs/api/csharp/yarn.unity.dialogueviewbase.runoptions.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.dialogueviewbase.runoptionsasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.|
|[UserRequestedViewAdvancement()](/docs/api/csharp/yarn.unity.dialogueviewbase.userrequestedviewadvancement.md)|Called by  <a href="yarn.unity.dialogueadvanceinput.md">DialogueAdvanceInput</a>  to signal that the user has requested that the dialogue advance.|

