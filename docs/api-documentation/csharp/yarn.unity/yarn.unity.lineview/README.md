# LineView

Class in [Yarn.Unity](../)

Inherits from [`DialogueViewBase`](../yarn.unity.dialogueviewbase/)

## Summary

A Dialogue View that presents lines of dialogue, using Unity UI elements.

```csharp
public class LineView : DialogueViewBase
```

## Methods

| Name                                                                                                        | Description                                                                                                                                                                                    |
| ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DialogueComplete()](yarn.unity.lineview.dialoguecomplete.md)                                               | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that the dialogue has ended, and no more lines will be delivered.                                                      |
| [DismissLine(Action)](yarn.unity.lineview.dismissline.md)                                                   | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that the view should dismiss its current line from display, and clean up.                                              |
| [GetPauseDurationsInsideLine(Markup.MarkupParseResult)](yarn.unity.lineview.getpausedurationsinsideline.md) | Creates a stack of typewriter pauses to use to temporarily halt the typewriter effect.                                                                                                         |
| [InterruptLine(LocalizedLine,Action)](yarn.unity.lineview.interruptline.md)                                 | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible. |
| [OnContinueClicked()](yarn.unity.lineview.oncontinueclicked.md)                                             | Called when the `Yarn.Unity.LineView.continueButton` is clicked.                                                                                                                               |
| [PaletteMarkedUpText(Markup.MarkupParseResult,MarkupPalette)](yarn.unity.lineview.palettemarkeduptext.md)   | Applies the `palette` to the line based on it's markup.                                                                                                                                        |
| [RunLine(LocalizedLine,Action)](yarn.unity.lineview.runline.md)                                             | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line should be displayed to the user.                                                                           |
| [UserRequestedViewAdvancement()](yarn.unity.lineview.userrequestedviewadvancement.md)                       | Called by [DialogueAdvanceInput](../yarn.unity.dialogueadvanceinput/) to signal that the user has requested that the dialogue advance.                                                         |
