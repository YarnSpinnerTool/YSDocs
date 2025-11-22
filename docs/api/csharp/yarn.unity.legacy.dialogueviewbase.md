# DialogueViewBase

Class in [Yarn.Unity.Legacy](yarn.unity.legacy.md)

Inherits from [`DialoguePresenterBase`](yarn.unity.dialoguepresenterbase.md)

{% hint style="warning" %}
This class is obsolete and may be removed from a future version of Yarn Spinner: Use DialoguePresenterBase.
{% endhint %}

## Summary

Implements the Yarn Spinner 2 callback-based API for dialogue views\
using Yarn Spinner 3.

```csharp
public abstract class DialogueViewBase : DialoguePresenterBase
```

## Remarks

You should not use this class in new code. It exists to provide a\
compatibility layer for existing Yarn Spinner dialogue views. New\
dialogue views should subclass [DialoguePresenterBase](yarn.unity.dialoguepresenterbase.md)\
directly.

## Fields

| Name                                                                       | Description                                                                                  |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| [requestInterrupt](yarn.unity.legacy.dialogueviewbase.requestinterrupt.md) | Represents the method that should be called when this view wants the line to be interrupted. |

## Methods

| Name                                                                                                           | Description                                                                                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DialogueComplete()](yarn.unity.legacy.dialogueviewbase.dialoguecomplete.md)                                   | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered.                                                      |
| [DialogueStarted()](yarn.unity.legacy.dialogueviewbase.dialoguestarted.md)                                     | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that dialogue has started.                                                                                             |
| [DismissLine(Action)](yarn.unity.legacy.dialogueviewbase.dismissline.md)                                       | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the view should dismiss its current line from display, and clean up.                                              |
| [InterruptLine(LocalizedLine,Action)](yarn.unity.legacy.dialogueviewbase.interruptline.md)                     | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible. |
| [OnDialogueCompleteAsync()](yarn.unity.legacy.dialogueviewbase.ondialoguecompleteasync.md)                     | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered.                                                      |
| [OnDialogueStartedAsync()](yarn.unity.legacy.dialogueviewbase.ondialoguestartedasync.md)                       | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that dialogue has started.                                                                                             |
| [RunLine(LocalizedLine,Action)](yarn.unity.legacy.dialogueviewbase.runline.md)                                 | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line should be displayed to the user.                                                                           |
| [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.legacy.dialogueviewbase.runlineasync.md)        | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line should be displayed to the user.                                                                           |
| [RunOptions(DialogueOption\[\],Action)](yarn.unity.legacy.dialogueviewbase.runoptions.md)                      | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.                                                                 |
| [RunOptionsAsync(DialogueOption\[\],CancellationToken)](yarn.unity.legacy.dialogueviewbase.runoptionsasync.md) | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.                                                                 |
| [UserRequestedViewAdvancement()](yarn.unity.legacy.dialogueviewbase.userrequestedviewadvancement.md)           | Called by [DialogueAdvanceInput](yarn.unity.legacy.dialogueadvanceinput.md) to signal that the user has requested that the dialogue advance.                                                  |
