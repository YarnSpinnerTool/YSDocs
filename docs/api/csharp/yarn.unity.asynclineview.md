# AsyncLineView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)

## Summary


A Dialogue View that presents lines of dialogue, using Unity UI
elements.


```csharp
public class AsyncLineView : AsyncDialogueViewBase
```

## Fields

|Name|Description|
|:---|:---|
|[autoAdvance](/docs/api/csharp/yarn.unity.asynclineview.autoadvance.md)|Controls whether this Line View will automatically to the Dialogue Runner that the line is complete as soon as the line has finished appearing.|
|[autoAdvanceDelay](/docs/api/csharp/yarn.unity.asynclineview.autoadvancedelay.md)|The amount of time after the line finishes appearing before automatically ending the line, in seconds.|
|[canvasGroup](/docs/api/csharp/yarn.unity.asynclineview.canvasgroup.md)|The canvas group that contains the UI elements used by this Line View.|
|[characterNameContainer](/docs/api/csharp/yarn.unity.asynclineview.characternamecontainer.md)|The game object that holds the  <a href="yarn.unity.asynclineview.characternametext.md">characterNameText</a>  text field.|
|[characterNameText](/docs/api/csharp/yarn.unity.asynclineview.characternametext.md)|The  <code>TMPro.TMP_Text</code>  object that displays the character names found in dialogue lines.|
|[continueButton](/docs/api/csharp/yarn.unity.asynclineview.continuebutton.md)|The  <code>UnityEngine.UI.Button</code>  that represents an on-screen button that the user can click to continue to the next piece of dialogue.|
|[fadeDownDuration](/docs/api/csharp/yarn.unity.asynclineview.fadedownduration.md)|The time that the fade effect will take to fade lines out.|
|[fadeUpDuration](/docs/api/csharp/yarn.unity.asynclineview.fadeupduration.md)|The time that the fade effect will take to fade lines in.|
|[lineText](/docs/api/csharp/yarn.unity.asynclineview.linetext.md)|The  <code>TMPro.TMP_Text</code>  object that displays the text of dialogue lines.|
|[onCharacterTyped](/docs/api/csharp/yarn.unity.asynclineview.oncharactertyped.md)|A Unity Event that is called each time a character is revealed during a typewriter effect.|
|[showCharacterNameInLineView](/docs/api/csharp/yarn.unity.asynclineview.showcharacternameinlineview.md)|Controls whether the  <a href="yarn.unity.asynclineview.linetext.md">lineText</a>  object will show the character name present in the line or not.|
|[temporalProcessors](/docs/api/csharp/yarn.unity.asynclineview.temporalprocessors.md)|A list of  <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a>  objects that will be used to handle markers in the line.|
|[typewriterEffectSpeed](/docs/api/csharp/yarn.unity.asynclineview.typewritereffectspeed.md)|The number of characters per second that should appear during a typewriter effect.|
|[useFadeEffect](/docs/api/csharp/yarn.unity.asynclineview.usefadeeffect.md)|Controls whether the line view should fade in when lines appear, and fade out when lines disappear.|
|[useTypewriterEffect](/docs/api/csharp/yarn.unity.asynclineview.usetypewritereffect.md)|Controls whether the text of  <a href="yarn.unity.asynclineview.linetext.md">lineText</a>  should be gradually revealed over time.|

## Methods

|Name|Description|
|:---|:---|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.asynclineview.ondialoguecompleteasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.asynclineview.ondialoguestartedasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that dialogue has started.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.asynclineview.runlineasync.md)|Presents a line using the configured text view.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.asynclineview.runoptionsasync.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.|

