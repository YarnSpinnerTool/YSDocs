# DialogueCharacterNameView

A subclass of [`DialogueViewBase`](../dialogueviewbase/) that displays character names.

```csharp
public class DialogueCharacterNameView : DialogueViewBase
```

## Remarks

This class uses the `character` attribute on lines that it receives to determine its content. When the view's [`RunLine(LocalizedLine, Action)`](dialoguecharacternameview.runline-localizedline-action.md) method is called with a line whose [`Text`](../localizedline/localizedline.text.md) contains a `character` attribute, the [`onNameUpdate`](dialoguecharacternameview.onnameupdate.md) event is fired. If the line does not contain such an attribute, the [`onNameNotPresent`](dialoguecharacternameview.onnamenotpresent.md) event is fired instead.

This view does not present any options or handle commands. It's intended to be used alongside other subclasses of DialogueViewBase.

## Methods

| Name | Description |
| :--- | :--- |
| [`DialogueStarted()`](dialoguecharacternameview.dialoguestarted.md) |  |
| [`DismissLine(Action)`](dialoguecharacternameview.dismissline-action.md) |  |
| [`OnLineStatusChanged(LocalizedLine)`](dialoguecharacternameview.onlinestatuschanged-localizedline.md) |  |
| [`RunLine(LocalizedLine, Action)`](dialoguecharacternameview.runline-localizedline-action.md) |  |
| [`RunOptions(DialogueOption[], Action<Int32>)`](dialoguecharacternameview.runoptions-dialogueoption-action-system.int32.md) |  |

## Fields

| Name | Description |
| :--- | :--- |
| [`onDialogueStarted`](dialoguecharacternameview.ondialoguestarted.md) | Invoked when the dialogue is started. |
| [`onNameNotPresent`](dialoguecharacternameview.onnamenotpresent.md) | Invoked when a line is received that doesn't contain a character name. |
| [`onNameUpdate`](dialoguecharacternameview.onnameupdate.md) | Invoked when a line is received that contains a character name. The name is given as the parameter. |

## See Also

* [`DialogueUI`](../dialogueui/): 

  Displays dialogue lines to the player, and sends user choices back

  to the dialogue system.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueCharacterNameView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueCharacterNameView.cs#L26), line 26.

