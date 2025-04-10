# AsyncOptionsView

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](yarn.unity.asyncdialogueviewbase.md)

## Summary

Receives options from a [DialogueRunner](yarn.unity.dialoguerunner.md) , and displays and manages a collection of [AsyncOptionItem](yarn.unity.asyncoptionitem.md) views for the user to choose from.

```csharp
public class AsyncOptionsView : AsyncDialogueViewBase
```

## Fields

| Name                                                                            | Description                                                                                                             |
| ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| [showUnavailableOptions](yarn.unity.asyncoptionsview.showunavailableoptions.md) | Controls whether or not to display options whose [IsAvailable](yarn.optionset.option.isavailable.md) value is `false` . |

## Methods

| Name                                                                                                    | Description                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [OnDialogueCompleteAsync()](yarn.unity.asyncoptionsview.ondialoguecompleteasync.md)                     | Called by a [DialogueRunner](yarn.unity.dialoguerunner.md) to dismiss the options view when dialogue is complete.                                                                      |
| [OnDialogueStartedAsync()](yarn.unity.asyncoptionsview.ondialoguestartedasync.md)                       | Called by a [DialogueRunner](yarn.unity.dialoguerunner.md) to set up the options view when dialogue begins.                                                                            |
| [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.asyncoptionsview.runlineasync.md)        | Called by a [DialogueRunner](yarn.unity.dialoguerunner.md) when a line needs to be presented, and stores the line as the 'last seen line' so that it can be shown when options appear. |
| [RunOptionsAsync(DialogueOption\[\],CancellationToken)](yarn.unity.asyncoptionsview.runoptionsasync.md) | Called by a [DialogueRunner](yarn.unity.dialoguerunner.md) to display a collection of options to the user.                                                                             |
