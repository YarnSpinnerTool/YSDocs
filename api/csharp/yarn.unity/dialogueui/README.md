# DialogueUI

Displays dialogue lines to the player, and sends user choices back to the dialogue system.

```csharp
public class DialogueUI : DialogueViewBase
```

## Remarks

The DialogueUI component works closely with the [`DialogueRunner`](../dialoguerunner/) class. It receives s,

s and s from the DialogueRunner, and conveys them to the rest of the game. It is also responsible for relaying input from the user to the DialogueRunner, such as option selection or the signal to proceed to the next line.

## Methods

| Name | Description |
| :--- | :--- |
| [`DialogueComplete()`](dialogueui.dialoguecomplete.md) |  |
| [`DialogueStarted()`](dialogueui.dialoguestarted.md) |  |
| [`DismissLine(System.Action)`](dialogueui.dismissline-system.action.md) |  |
| [`DoRunLine(LocalizedLine, System.Action)`](dialogueui.dorunline-localizedline-system.action.md) | Shows a line of dialogue, gradually. |
| [`OnLineStatusChanged(LocalizedLine)`](dialogueui.onlinestatuschanged-localizedline.md) |  |
| [`RunLine(LocalizedLine, System.Action)`](dialogueui.runline-localizedline-system.action.md) |  |
| [`RunOptions(DialogueOption[], System.Action<Int32>)`](dialogueui.runoptions-dialogueoption-system.action-system.int32.md) |  |
| [`SelectOption(Int32)`](dialogueui.selectoption-system.int32.md) | Signals that the user has selected an option. |

## Fields

| Name | Description |
| :--- | :--- |
| [`dialogueContainer`](dialogueui.dialoguecontainer.md) | The object that contains the dialogue and the options. |
| [`onDialogueEnd`](dialogueui.ondialogueend.md) | A  that is called when the dialogue ends. |
| [`onDialogueStart`](dialogueui.ondialoguestart.md) | A  that is called when the dialogue starts. |
| [`onLineEnd`](dialogueui.onlineend.md) | A  that is called when a line has finished displaying, and should be removed from the screen. |
| [`onLineFinishDisplaying`](dialogueui.onlinefinishdisplaying.md) | A  that is called when a line has finished being delivered on all views. |
| [`onLineStart`](dialogueui.onlinestart.md) | A  that is called when a  has been delivered. |
| [`onLineUpdate`](dialogueui.onlineupdate.md) | A [`DialogueRunner.StringUnityEvent`](../dialoguerunner.stringunityevent.md) that is called when the visible part of the line's localised text changes. |
| [`onOptionsEnd`](dialogueui.onoptionsend.md) | A  that is called when an option has been selected, and the [`optionButtons`](dialogueui.optionbuttons.md) should be hidden. |
| [`onOptionsStart`](dialogueui.onoptionsstart.md) | A  that is called when an  has been displayed to the user. |
| [`onTextFinishDisplaying`](dialogueui.ontextfinishdisplaying.md) | A  that is called when the line has finished being displayed by this view. |
| [`optionButtons`](dialogueui.optionbuttons.md) | The buttons that let the user choose an option. |
| [`showCharacterName`](dialogueui.showcharactername.md) | Indicates whether lines should display character names, if present. |
| [`showUnavailableOptions`](dialogueui.showunavailableoptions.md) | Indicates whether options whose line conditions have evaluated to false should be shown \(but be unselectable\). If this value is false, these options are not shown at all. |
| [`textSpeed`](dialogueui.textspeed.md) | How quickly to show the text, in seconds per character |

## See Also

* [`DialogueRunner`](../dialoguerunner/): 

  The \[DialogueRunner\]\({{&lt;ref

  "/docs/unity/components/dialogue-runner.md"&gt;}}\) component acts as

  the interface between your game and Yarn Spinner.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L48), line 48.

