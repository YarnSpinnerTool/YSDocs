# DialogueUI Class

Displays dialogue lines to the player, and sends user choices back
to the dialogue system.


```csharp
public class DialogueUI : DialogueViewBase
```
## Remarks

The DialogueUI component works closely with the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) class. It receives <see cref="!:Line"></see>s,
<see cref="!:OptionSet"></see>s and <see cref="!:Command"></see>s from the
DialogueRunner, and conveys them to the rest of the game. It is
also responsible for relaying input from the user to the
DialogueRunner, such as option selection or the signal to proceed
to the next line.




## Methods
|Name|Description|
|:---|:---|
|[`DialogueComplete()`](/api/csharp/yarn.unity/dialogueui.dialoguecomplete.md)||
|[`DialogueStarted()`](/api/csharp/yarn.unity/dialogueui.dialoguestarted.md)||
|[`DismissLine(System.Action)`](/api/csharp/yarn.unity/dialogueui.dismissline-system.action-.md)||
|[`DoRunLine(LocalizedLine, System.Action)`](/api/csharp/yarn.unity/dialogueui.dorunline-localizedline,system.action-.md)| Shows a line of dialogue, gradually. |
|[`OnLineStatusChanged(LocalizedLine)`](/api/csharp/yarn.unity/dialogueui.onlinestatuschanged-localizedline-.md)||
|[`RunLine(LocalizedLine, System.Action)`](/api/csharp/yarn.unity/dialogueui.runline-localizedline,system.action-.md)||
|[`RunOptions(DialogueOption[], System.Action<Int32>)`](/api/csharp/yarn.unity/dialogueui.runoptions-dialogueoption--,system.action-system.int32--.md)||
|[`SelectOption(Int32)`](/api/csharp/yarn.unity/dialogueui.selectoption-system.int32-.md)| Signals that the user has selected an option. |
## Fields
|Name|Description|
|:---|:---|
|[`dialogueContainer`](/api/csharp/yarn.unity/dialogueui.dialoguecontainer.md)| The object that contains the dialogue and the options. |
|[`onDialogueEnd`](/api/csharp/yarn.unity/dialogueui.ondialogueend.md)| A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called when the dialogue ends. |
|[`onDialogueStart`](/api/csharp/yarn.unity/dialogueui.ondialoguestart.md)| A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called when the dialogue starts. |
|[`onLineEnd`](/api/csharp/yarn.unity/dialogueui.onlineend.md)| A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called when a line has finished displaying, and should be removed from the screen. |
|[`onLineFinishDisplaying`](/api/csharp/yarn.unity/dialogueui.onlinefinishdisplaying.md)| A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called when a line has finished being delivered on all views. |
|[`onLineStart`](/api/csharp/yarn.unity/dialogueui.onlinestart.md)| A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called when a <see cref="!:Line"></see> has been delivered. |
|[`onLineUpdate`](/api/csharp/yarn.unity/dialogueui.onlineupdate.md)| A [`DialogueRunner.StringUnityEvent`](/api/csharp/yarn.unity/dialoguerunner.stringunityevent.md) that is called when the visible part of the line's localised text changes. |
|[`onOptionsEnd`](/api/csharp/yarn.unity/dialogueui.onoptionsend.md)| A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called when an option has been selected, and the [`optionButtons`](/api/csharp/yarn.unity/dialogueui.optionbuttons.md) should be hidden. |
|[`onOptionsStart`](/api/csharp/yarn.unity/dialogueui.onoptionsstart.md)| A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called when an <see cref="!:OptionSet"></see> has been displayed to the user. |
|[`onTextFinishDisplaying`](/api/csharp/yarn.unity/dialogueui.ontextfinishdisplaying.md)| A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called when the line has finished being displayed by this view. |
|[`optionButtons`](/api/csharp/yarn.unity/dialogueui.optionbuttons.md)| The buttons that let the user choose an option. |
|[`showCharacterName`](/api/csharp/yarn.unity/dialogueui.showcharactername.md)| Indicates whether lines should display character names, if present. |
|[`showUnavailableOptions`](/api/csharp/yarn.unity/dialogueui.showunavailableoptions.md)| Indicates whether options whose line conditions have evaluated to false should be shown (but be unselectable). If this value is false, these options are not shown at all. |
|[`textSpeed`](/api/csharp/yarn.unity/dialogueui.textspeed.md)| How quickly to show the text, in seconds per character |
## See Also
* [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md): 
The [DialogueRunner]({{<ref
"/docs/unity/components/dialogue-runner.md">}}) component acts as
the interface between your game and Yarn Spinner.

<div class="class-metadata">

Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L48), line 48.
