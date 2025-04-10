# DialogueCharacterNameView

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](yarn.unity.asyncdialogueviewbase.md)

## Summary

A subclass of [DialogueViewBase](yarn.unity.dialogueviewbase.md) that displays character names.

```csharp
public class DialogueCharacterNameView : AsyncDialogueViewBase
```

## Remarks

This class uses the \`character\` attribute on lines that it receives to determine its content. When the view's [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.dialoguecharacternameview.runlineasync.md) method is called with a line whose [Text](yarn.unity.localizedline.text.md) contains a \`character\` attribute, the [onNameUpdate](yarn.unity.dialoguecharacternameview.onnameupdate.md) event is fired. If the line does not contain such an attribute, the [onNameNotPresent](yarn.unity.dialoguecharacternameview.onnamenotpresent.md) event is fired instead.

This view does not present any options or handle commands. It's intended to be used alongside other subclasses of [AsyncDialogueViewBase](yarn.unity.asyncdialogueviewbase.md).

## Fields

| Name                                                                           | Description                                                                                         |
| ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| [onDialogueStarted](yarn.unity.dialoguecharacternameview.ondialoguestarted.md) | Invoked when the dialogue is started.                                                               |
| [onNameNotPresent](yarn.unity.dialoguecharacternameview.onnamenotpresent.md)   | Invoked when a line is received that doesn't contain a character name.                              |
| [onNameUpdate](yarn.unity.dialoguecharacternameview.onnameupdate.md)           | Invoked when a line is received that contains a character name. The name is given as the parameter. |

## Methods

| Name                                                                                                             | Description                                                                                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [OnDialogueCompleteAsync()](yarn.unity.dialoguecharacternameview.ondialoguecompleteasync.md)                     | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered.                                                                       |
| [OnDialogueStartedAsync()](yarn.unity.dialoguecharacternameview.ondialoguestartedasync.md)                       | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that dialogue has started.                                                                                                              |
| [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.dialoguecharacternameview.runlineasync.md)        | Invokes the [onNameUpdate](yarn.unity.dialoguecharacternameview.onnameupdate.md) or [onNameNotPresent](yarn.unity.dialoguecharacternameview.onnamenotpresent.md) events, depending on the contents of `line` . |
| [RunOptionsAsync(DialogueOption\[\],CancellationToken)](yarn.unity.dialoguecharacternameview.runoptionsasync.md) | Takes no action; this dialogue view does not handle options.                                                                                                                                                   |
