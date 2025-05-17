# LinePresenter

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`DialoguePresenterBase`](/docs/api/csharp/yarn.unity.dialoguepresenterbase.md)

## Summary


A Dialogue View that presents lines of dialogue, using Unity UI
elements.


```csharp
public sealed class LinePresenter : DialoguePresenterBase
```

## Fields

|Name|Description|
|:---|:---|
|[autoAdvance](/docs/api/csharp/yarn.unity.linepresenter.autoadvance.md)|Controls whether this Line View will automatically to the Dialogue Runner that the line is complete as soon as the line has finished appearing.|
|[autoAdvanceDelay](/docs/api/csharp/yarn.unity.linepresenter.autoadvancedelay.md)|The amount of time after the line finishes appearing before automatically ending the line, in seconds.|
|[canvasGroup](/docs/api/csharp/yarn.unity.linepresenter.canvasgroup.md)|The canvas group that contains the UI elements used by this Line View.|
|[characterNameContainer](/docs/api/csharp/yarn.unity.linepresenter.characternamecontainer.md)|The game object that holds the  <a href="yarn.unity.linepresenter.characternametext.md">characterNameText</a>  text field.|
|[characterNameText](/docs/api/csharp/yarn.unity.linepresenter.characternametext.md)|The  <code>TMPro.TMP_Text</code>  object that displays the character names found in dialogue lines.|
|[fadeDownDuration](/docs/api/csharp/yarn.unity.linepresenter.fadedownduration.md)|The time that the fade effect will take to fade lines out.|
|[fadeUpDuration](/docs/api/csharp/yarn.unity.linepresenter.fadeupduration.md)|The time that the fade effect will take to fade lines in.|
|[lineText](/docs/api/csharp/yarn.unity.linepresenter.linetext.md)|The  <code>TMPro.TMP_Text</code>  object that displays the text of dialogue lines.|
|[showCharacterNameInLineView](/docs/api/csharp/yarn.unity.linepresenter.showcharacternameinlineview.md)|Controls whether the  <a href="yarn.unity.linepresenter.linetext.md">lineText</a>  object will show the character name present in the line or not.|
|[temporalProcessors](/docs/api/csharp/yarn.unity.linepresenter.temporalprocessors.md)||
|[typewriterEffectSpeed](/docs/api/csharp/yarn.unity.linepresenter.typewritereffectspeed.md)|The number of characters per second that should appear during a typewriter effect.|
|[useFadeEffect](/docs/api/csharp/yarn.unity.linepresenter.usefadeeffect.md)|Controls whether the line view should fade in when lines appear, and fade out when lines disappear.|
|[useTypewriterEffect](/docs/api/csharp/yarn.unity.linepresenter.usetypewritereffect.md)|Controls whether the text of  <a href="yarn.unity.linepresenter.linetext.md">lineText</a>  should be gradually revealed over time.|

## Methods

|Name|Description|
|:---|:---|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.linepresenter.ondialoguecompleteasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.linepresenter.ondialoguestartedasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that dialogue has started.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.linepresenter.runlineasync.md)|Presents a line using the configured text view.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.linepresenter.runoptionsasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.|

