# AsyncOptionsView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)

## Summary


Receives options from a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> , and displays and
manages a collection of  <a href="yarn.unity.asyncoptionitem.md">AsyncOptionItem</a>  views for the user
to choose from.


```csharp
public class AsyncOptionsView : AsyncDialogueViewBase
```

## Fields

|Name|Description|
|:---|:---|
|[showUnavailableOptions](/docs/api/csharp/yarn.unity.asyncoptionsview.showunavailableoptions.md)|Controls whether or not to display options whose  <a href="yarn.optionset.option.isavailable.md">IsAvailable</a>  value is  <code>false</code> .|

## Methods

|Name|Description|
|:---|:---|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.asyncoptionsview.ondialoguecompleteasync.md)|Called by a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to dismiss the options view when dialogue is complete.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.asyncoptionsview.ondialoguestartedasync.md)|Called by a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to set up the options view when dialogue begins.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.asyncoptionsview.runlineasync.md)|Called by a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  when a line needs to be presented, and stores the line as the 'last seen line' so that it can be shown when options appear.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.asyncoptionsview.runoptionsasync.md)|Called by a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to display a collection of options to the user.|

