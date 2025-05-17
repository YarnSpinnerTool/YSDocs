# OptionsPresenter

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`DialoguePresenterBase`](/docs/api/csharp/yarn.unity.dialoguepresenterbase.md)

## Summary


Receives options from a  [DialogueRunner](yarn.unity.dialoguerunner.md) , and displays and
manages a collection of  [OptionItem](yarn.unity.optionitem.md)  views for the user
to choose from.


```csharp
public sealed class OptionsPresenter : DialoguePresenterBase
```

## Fields

|Name|Description|
|:---|:---|
|[fadeDownDuration](/docs/api/csharp/yarn.unity.optionspresenter.fadedownduration.md)||
|[fadeUpDuration](/docs/api/csharp/yarn.unity.optionspresenter.fadeupduration.md)||
|[showUnavailableOptions](/docs/api/csharp/yarn.unity.optionspresenter.showunavailableoptions.md)|Controls whether or not to display options whose  [IsAvailable](yarn.optionset.option.isavailable.md)  value is  `false` .|
|[useFadeEffect](/docs/api/csharp/yarn.unity.optionspresenter.usefadeeffect.md)||

## Methods

|Name|Description|
|:---|:---|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.optionspresenter.ondialoguecompleteasync.md)|Called by a  [DialogueRunner](yarn.unity.dialoguerunner.md)  to dismiss the options view when dialogue is complete.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.optionspresenter.ondialoguestartedasync.md)|Called by a  [DialogueRunner](yarn.unity.dialoguerunner.md)  to set up the options view when dialogue begins.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.optionspresenter.runlineasync.md)|Called by a  [DialogueRunner](yarn.unity.dialoguerunner.md)  when a line needs to be presented, and stores the line as the 'last seen line' so that it can be shown when options appear.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.optionspresenter.runoptionsasync.md)|Called by a  [DialogueRunner](yarn.unity.dialoguerunner.md)  to display a collection of options to the user.|

