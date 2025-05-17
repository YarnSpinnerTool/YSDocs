# LineView

Class in [Yarn.Unity.Legacy](/docs/api/csharp/yarn.unity.legacy.md)

Inherits from [`DialogueViewBase`](/docs/api/csharp/yarn.unity.legacy.dialogueviewbase.md)

{% hint style="warning" %}
This class is <b>obsolete</b> and may be removed from a future version of Yarn Spinner.
{% endhint %}

## Summary


A Dialogue View that presents lines of dialogue, using Unity UI
elements.


```csharp
public class LineView : DialogueViewBase
```

## Fields

|Name|Description|
|:---|:---|
|[autoAdvance](/docs/api/csharp/yarn.unity.legacy.lineview.autoadvance.md)|Controls whether this Line View will wait for user input before indicating that it has finished presenting a line.|
|[canvasGroup](/docs/api/csharp/yarn.unity.legacy.lineview.canvasgroup.md)|The canvas group that contains the UI elements used by this Line View.|
|[characterNameContainer](/docs/api/csharp/yarn.unity.legacy.lineview.characternamecontainer.md)|The gameobject that holds the  [characterNameText](yarn.unity.legacy.lineview.characternametext.md)  textfield.|
|[characterNameText](/docs/api/csharp/yarn.unity.legacy.lineview.characternametext.md)|The  `TMPro.TextMeshProUGUI`  object that displays the character names found in dialogue lines.|
|[continueButton](/docs/api/csharp/yarn.unity.legacy.lineview.continuebutton.md)|The game object that represents an on-screen button that the user can click to continue to the next piece of dialogue.|
|[fadeInTime](/docs/api/csharp/yarn.unity.legacy.lineview.fadeintime.md)|The time that the fade effect will take to fade lines in.|
|[fadeOutTime](/docs/api/csharp/yarn.unity.legacy.lineview.fadeouttime.md)|The time that the fade effect will take to fade lines out.|
|[holdTime](/docs/api/csharp/yarn.unity.legacy.lineview.holdtime.md)|The amount of time to wait after any line|
|[lineText](/docs/api/csharp/yarn.unity.legacy.lineview.linetext.md)|The  `TMPro.TextMeshProUGUI`  object that displays the text of dialogue lines.|
|[onCharacterTyped](/docs/api/csharp/yarn.unity.legacy.lineview.oncharactertyped.md)|A Unity Event that is called each time a character is revealed during a typewriter effect.|
|[onPauseEnded](/docs/api/csharp/yarn.unity.legacy.lineview.onpauseended.md)|A Unity Event that is called when a pause inside of the typewriter effect finishes and the typewriter has started once again.|
|[onPauseStarted](/docs/api/csharp/yarn.unity.legacy.lineview.onpausestarted.md)|A Unity Event that is called when a pause inside of the typewriter effect occurs.|
|[palette](/docs/api/csharp/yarn.unity.legacy.lineview.palette.md)||
|[showCharacterNameInLineView](/docs/api/csharp/yarn.unity.legacy.lineview.showcharacternameinlineview.md)|Controls whether the  [lineText](yarn.unity.legacy.lineview.linetext.md)  object will show the character name present in the line or not.|
|[typewriterEffectSpeed](/docs/api/csharp/yarn.unity.legacy.lineview.typewritereffectspeed.md)|The number of characters per second that should appear during a typewriter effect.|
|[useFadeEffect](/docs/api/csharp/yarn.unity.legacy.lineview.usefadeeffect.md)|Controls whether the line view should fade in when lines appear, and fade out when lines disappear.|
|[useTypewriterEffect](/docs/api/csharp/yarn.unity.legacy.lineview.usetypewritereffect.md)|Controls whether the text of  [lineText](yarn.unity.legacy.lineview.linetext.md)  should be gradually revealed over time.|

## Methods

|Name|Description|
|:---|:---|
|[AddLineBreaks(Markup.MarkupParseResult)](/docs/api/csharp/yarn.unity.legacy.lineview.addlinebreaks.md)|Inserts TextMeshPro line break markup in a line where Yarn line break attributes appear.|
|[DialogueComplete()](/docs/api/csharp/yarn.unity.legacy.lineview.dialoguecomplete.md)|Called by the  [DialogueRunner](yarn.unity.dialoguerunner.md)  to signal that the dialogue has ended, and no more lines will be delivered.|
|[DismissLine(Action)](/docs/api/csharp/yarn.unity.legacy.lineview.dismissline.md)|Called by the  [DialogueRunner](yarn.unity.dialoguerunner.md)  to signal that the view should dismiss its current line from display, and clean up.|
|[InterruptLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.legacy.lineview.interruptline.md)|Called by the  [DialogueRunner](yarn.unity.dialoguerunner.md)  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.|
|[OnContinueClicked()](/docs/api/csharp/yarn.unity.legacy.lineview.oncontinueclicked.md)|Called when the  [continueButton](yarn.unity.legacy.lineview.continuebutton.md)  is clicked.|
|[PaletteMarkedUpText(Markup.MarkupParseResult,MarkupPalette,bool)](/docs/api/csharp/yarn.unity.legacy.lineview.palettemarkeduptext.md)|Applies the  `palette`  to the line based on it's markup.|
|[RunLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.legacy.lineview.runline.md)|Called by the  [DialogueRunner](yarn.unity.dialoguerunner.md)  to signal that a line should be displayed to the user.|
|[UserRequestedViewAdvancement()](/docs/api/csharp/yarn.unity.legacy.lineview.userrequestedviewadvancement.md)|Called by  [DialogueAdvanceInput](yarn.unity.legacy.dialogueadvanceinput.md)  to signal that the user has requested that the dialogue advance.|

