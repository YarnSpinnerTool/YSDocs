# LineView

Class in [Yarn.Unity](api/csharp/yarn.unity.md)

Inherits from [`DialogueViewBase`](api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


A Dialogue View that presents lines of dialogue, using Unity UI
elements.


```csharp
public class LineView : DialogueViewBase
```

## Methods

|Name|Description|
|:---|:---|
|[DismissLine(Action)](api/csharp/yarn.unity.lineview.dismissline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.|
|[InterruptLine(LocalizedLine,Action)](api/csharp/yarn.unity.lineview.interruptline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.|
|[OnContinueClicked()](api/csharp/yarn.unity.lineview.oncontinueclicked.md)|Called when the  <code>Yarn.Unity.LineView.continueButton</code>  is clicked.|
|[RunLine(LocalizedLine,Action)](api/csharp/yarn.unity.lineview.runline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.|
|[UserRequestedViewAdvancement()](api/csharp/yarn.unity.lineview.userrequestedviewadvancement.md)|Called by  <a href="yarn.unity.dialogueadvanceinput.md">DialogueAdvanceInput</a>  to signal that the user has requested that the dialogue advance.|

