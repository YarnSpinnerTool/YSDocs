# LineView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`DialogueViewBase`](/docs/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


A Dialogue View that presents lines of dialogue, using Unity UI
elements.


```csharp
public class LineView : DialogueViewBase
```

## Fields

|Name|Description|
|:---|:---|
|[autoAdvance](/docs/api/csharp/yarn.unity.lineview.autoadvance.md)|Controls whether this Line View will wait for user input before indicating that it has finished presenting a line.|
|[canvasGroup](/docs/api/csharp/yarn.unity.lineview.canvasgroup.md)|The canvas group that contains the UI elements used by this Line View.|
|[characterNameContainer](/docs/api/csharp/yarn.unity.lineview.characternamecontainer.md)|The gameobject that holds the  <a href="yarn.unity.lineview.characternametext.md">characterNameText</a>  textfield.|
|[characterNameText](/docs/api/csharp/yarn.unity.lineview.characternametext.md)|The  <code>TMPro.TextMeshProUGUI</code>  object that displays the character names found in dialogue lines.|
|[continueButton](/docs/api/csharp/yarn.unity.lineview.continuebutton.md)|The game object that represents an on-screen button that the user can click to continue to the next piece of dialogue.|
|[fadeInTime](/docs/api/csharp/yarn.unity.lineview.fadeintime.md)|The time that the fade effect will take to fade lines in.|
|[fadeOutTime](/docs/api/csharp/yarn.unity.lineview.fadeouttime.md)|The time that the fade effect will take to fade lines out.|
|[holdTime](/docs/api/csharp/yarn.unity.lineview.holdtime.md)|The amount of time to wait after any line|
|[lineText](/docs/api/csharp/yarn.unity.lineview.linetext.md)|The  <code>TMPro.TextMeshProUGUI</code>  object that displays the text of dialogue lines.|
|[onCharacterTyped](/docs/api/csharp/yarn.unity.lineview.oncharactertyped.md)|A Unity Event that is called each time a character is revealed during a typewriter effect.|
|[onPauseEnded](/docs/api/csharp/yarn.unity.lineview.onpauseended.md)|A Unity Event that is called when a pause inside of the typewriter effect finishes and the typewriter has started once again.|
|[onPauseStarted](/docs/api/csharp/yarn.unity.lineview.onpausestarted.md)|A Unity Event that is called when a pause inside of the typewriter effect occurs.|
|[palette](/docs/api/csharp/yarn.unity.lineview.palette.md)||
|[showCharacterNameInLineView](/docs/api/csharp/yarn.unity.lineview.showcharacternameinlineview.md)|Controls whether the  <a href="yarn.unity.lineview.linetext.md">lineText</a>  object will show the character name present in the line or not.|
|[typewriterEffectSpeed](/docs/api/csharp/yarn.unity.lineview.typewritereffectspeed.md)|The number of characters per second that should appear during a typewriter effect.|
|[useFadeEffect](/docs/api/csharp/yarn.unity.lineview.usefadeeffect.md)|Controls whether the line view should fade in when lines appear, and fade out when lines disappear.|
|[useTypewriterEffect](/docs/api/csharp/yarn.unity.lineview.usetypewritereffect.md)|Controls whether the text of  <a href="yarn.unity.lineview.linetext.md">lineText</a>  should be gradually revealed over time.|

## Methods

|Name|Description|
|:---|:---|
|[AddLineBreaks(Markup.MarkupParseResult)](/docs/api/csharp/yarn.unity.lineview.addlinebreaks.md)||
|[DialogueComplete()](/docs/api/csharp/yarn.unity.lineview.dialoguecomplete.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[DismissLine(Action)](/docs/api/csharp/yarn.unity.lineview.dismissline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.|
|[GetPauseDurationsInsideLine(Markup.MarkupParseResult)](/docs/api/csharp/yarn.unity.lineview.getpausedurationsinsideline.md)|Creates a stack of typewriter pauses to use to temporarily halt the typewriter effect.|
|[InterruptLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.lineview.interruptline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.|
|[OnContinueClicked()](/docs/api/csharp/yarn.unity.lineview.oncontinueclicked.md)|Called when the  <a href="yarn.unity.lineview.continuebutton.md">continueButton</a>  is clicked.|
|[PaletteMarkedUpText(Markup.MarkupParseResult,MarkupPalette,bool)](/docs/api/csharp/yarn.unity.lineview.palettemarkeduptext.md)|Applies the  <code>palette</code>  to the line based on it's markup.|
|[RunLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.lineview.runline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.|
|[UserRequestedViewAdvancement()](/docs/api/csharp/yarn.unity.lineview.userrequestedviewadvancement.md)|Called by  <a href="yarn.unity.dialogueadvanceinput.md">DialogueAdvanceInput</a>  to signal that the user has requested that the dialogue advance.|

