# CharacterColorView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)

## Summary


A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that updates the colour of
a  <code>TMPro.TMP_Text</code>  object based on the character speaking a
line. names.


```csharp
public class CharacterColorView : Yarn.Unity.AsyncDialogueViewBase
```

## Remarks

<p>This class uses the `character` attribute on lines that it
receives to determine its content. When the view's <a href="yarn.unity.charactercolorview.runlineasync.md">RunLineAsync(LocalizedLine,LineCancellationToken)</a> method is called with a line whose <a href="yarn.unity.localizedline.text.md">Text</a> contains a `character` attribute, the text
views have their <code>TMPro.TMP_Text.color</code> property updated
based on the colours configured in the Inspector.
</p> <p>This view does not present any options or handle commands. It's
intended to be used alongside other subclasses of <a href="yarn.unity.asyncdialogueviewbase.md">AsyncDialogueViewBase</a>.</p>

## Classes

|Name|Description|
|:---|:---|
|[CharacterColorData](/docs/api/csharp/yarn.unity.charactercolorview.charactercolordata.md)|Associates a named character with a colour to use in a  <a href="yarn.unity.charactercolorview.md">CharacterColorView</a> .|

## Methods

|Name|Description|
|:---|:---|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.charactercolorview.ondialoguecompleteasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.charactercolorview.ondialoguestartedasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that dialogue has started.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.charactercolorview.runlineasync.md)|Updates the text colour of  <code>Yarn.Unity.CharacterColorView.lineTexts</code>  based on the character name of  <code>line</code> , if any.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.charactercolorview.runoptionsasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.|

