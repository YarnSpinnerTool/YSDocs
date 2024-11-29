# DialogueCharacterNameView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)

## Summary


A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that displays character
names.


```csharp
public class DialogueCharacterNameView : AsyncDialogueViewBase
```

## Remarks

<p>This class uses the `character` attribute on lines that it
receives to determine its content. When the view's <a href="yarn.unity.dialoguecharacternameview.runlineasync.md">RunLineAsync(LocalizedLine,LineCancellationToken)</a> method is called with a line whose <a href="yarn.unity.localizedline.text.md">Text</a> contains a `character` attribute, the <a href="yarn.unity.dialoguecharacternameview.onnameupdate.md">onNameUpdate</a> event is fired. If the line does not contain such
an attribute, the <a href="yarn.unity.dialoguecharacternameview.onnamenotpresent.md">onNameNotPresent</a> event is fired
instead.</p> <p>This view does not present any options or handle commands. It's
intended to be used alongside other subclasses of <a href="yarn.unity.asyncdialogueviewbase.md">AsyncDialogueViewBase</a>.</p>

## Fields

|Name|Description|
|:---|:---|
|[onDialogueStarted](/docs/api/csharp/yarn.unity.dialoguecharacternameview.ondialoguestarted.md)|Invoked when the dialogue is started.|
|[onNameNotPresent](/docs/api/csharp/yarn.unity.dialoguecharacternameview.onnamenotpresent.md)|Invoked when a line is received that doesn't contain a character name.|
|[onNameUpdate](/docs/api/csharp/yarn.unity.dialoguecharacternameview.onnameupdate.md)|Invoked when a line is received that contains a character name. The name is given as the parameter.|

## Methods

|Name|Description|
|:---|:---|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.dialoguecharacternameview.ondialoguecompleteasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.dialoguecharacternameview.ondialoguestartedasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that dialogue has started.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.dialoguecharacternameview.runlineasync.md)|Invokes the  <a href="yarn.unity.dialoguecharacternameview.onnameupdate.md">onNameUpdate</a>  or  <a href="yarn.unity.dialoguecharacternameview.onnamenotpresent.md">onNameNotPresent</a>  events, depending on the contents of <code>line</code> .|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.dialoguecharacternameview.runoptionsasync.md)|Takes no action; this dialogue view does not handle options.|

