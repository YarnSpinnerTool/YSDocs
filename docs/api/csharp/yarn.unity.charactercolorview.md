# CharacterColorView

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](yarn.unity.asyncdialogueviewbase.md)

## Summary

A subclass of [DialogueViewBase](yarn.unity.dialogueviewbase.md) that updates the colour of a `TMPro.TMP_Text` object based on the character speaking a line. names.

```csharp
public class CharacterColorView : Yarn.Unity.AsyncDialogueViewBase
```

## Remarks

This class uses the \`character\` attribute on lines that it receives to determine its content. When the view's [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.charactercolorview.runlineasync.md) method is called with a line whose [Text](yarn.unity.localizedline.text.md) contains a \`character\` attribute, the text views have their `TMPro.TMP_Text.color` property updated based on the colours configured in the Inspector.

This view does not present any options or handle commands. It's intended to be used alongside other subclasses of [AsyncDialogueViewBase](yarn.unity.asyncdialogueviewbase.md).

## Classes

| Name                                                                      | Description                                                                                                     |
| ------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| [CharacterColorData](yarn.unity.charactercolorview.charactercolordata.md) | Associates a named character with a colour to use in a [CharacterColorView](yarn.unity.charactercolorview.md) . |

## Methods

| Name                                                                                                      | Description                                                                                                                              |
| --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| [OnDialogueCompleteAsync()](yarn.unity.charactercolorview.ondialoguecompleteasync.md)                     | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered. |
| [OnDialogueStartedAsync()](yarn.unity.charactercolorview.ondialoguestartedasync.md)                       | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that dialogue has started.                                        |
| [RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.charactercolorview.runlineasync.md)        | Updates the text colour of `Yarn.Unity.CharacterColorView.lineTexts` based on the character name of `line` , if any.                     |
| [RunOptionsAsync(DialogueOption\[\],CancellationToken)](yarn.unity.charactercolorview.runoptionsasync.md) | Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.            |
