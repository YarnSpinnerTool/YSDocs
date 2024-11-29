# LineView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`DialogueViewBase`](/docs/api/csharp/yarn.unity.dialogueviewbase.md)

{% hint style="warning" %}
This class is <b>obsolete</b> and may be removed from a future version of Yarn Spinner.
{% endhint %}

## Summary


A Dialogue View that presents lines of dialogue, using Unity UI
elements.


```csharp
public class LineView : DialogueViewBase
```

## Methods

|Name|Description|
|:---|:---|
|[AddLineBreaks(Markup.MarkupParseResult)](/docs/api/csharp/yarn.unity.lineview.addlinebreaks.md)|Inserts TextMeshPro line break markup in a line where Yarn line break attributes appear.|
|[DialogueComplete()](/docs/api/csharp/yarn.unity.lineview.dialoguecomplete.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[DismissLine(Action)](/docs/api/csharp/yarn.unity.lineview.dismissline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.|
|[InterruptLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.lineview.interruptline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.|
|[OnContinueClicked()](/docs/api/csharp/yarn.unity.lineview.oncontinueclicked.md)|Called when the  <code>Yarn.Unity.LineView.continueButton</code>  is clicked.|
|[PaletteMarkedUpText(Markup.MarkupParseResult,MarkupPalette,bool)](/docs/api/csharp/yarn.unity.lineview.palettemarkeduptext.md)|Applies the  <code>palette</code>  to the line based on it's markup.|
|[RunLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.lineview.runline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.|
|[UserRequestedViewAdvancement()](/docs/api/csharp/yarn.unity.lineview.userrequestedviewadvancement.md)|Called by  <a href="yarn.unity.dialogueadvanceinput.md">DialogueAdvanceInput</a>  to signal that the user has requested that the dialogue advance.|

