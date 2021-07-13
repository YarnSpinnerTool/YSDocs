# DialogueCharacterNameView Class

A subclass of [`DialogueViewBase`](/api/csharp/yarn.unity/dialogueviewbase.md) that displays
character names.


```csharp
public class DialogueCharacterNameView : DialogueViewBase
```
## Remarks

This class uses the `character` attribute on lines that it receives
to determine its content. When the view's [`RunLine(LocalizedLine, Action)`](/api/csharp/yarn.unity/dialoguecharacternameview.runline-localizedline,action-.md)
method is called with a line whose [`Text`](/api/csharp/yarn.unity/localizedline.text.md)
contains a `character` attribute, the [`onNameUpdate`](/api/csharp/yarn.unity/dialoguecharacternameview.onnameupdate.md)
event is fired. If the line does not contain such an attribute, the
[`onNameNotPresent`](/api/csharp/yarn.unity/dialoguecharacternameview.onnamenotpresent.md) event is fired instead.

This view does not present any options or handle commands. It's
intended to be used alongside other subclasses of DialogueViewBase.




## Methods
|Name|Description|
|:---|:---|
|[`DialogueStarted()`](/api/csharp/yarn.unity/dialoguecharacternameview.dialoguestarted.md)||
|[`DismissLine(Action)`](/api/csharp/yarn.unity/dialoguecharacternameview.dismissline-action-.md)||
|[`OnLineStatusChanged(LocalizedLine)`](/api/csharp/yarn.unity/dialoguecharacternameview.onlinestatuschanged-localizedline-.md)||
|[`RunLine(LocalizedLine, Action)`](/api/csharp/yarn.unity/dialoguecharacternameview.runline-localizedline,action-.md)||
|[`RunOptions(DialogueOption[], Action<Int32>)`](/api/csharp/yarn.unity/dialoguecharacternameview.runoptions-dialogueoption--,action-system.int32--.md)||
## Fields
|Name|Description|
|:---|:---|
|[`onDialogueStarted`](/api/csharp/yarn.unity/dialoguecharacternameview.ondialoguestarted.md)| Invoked when the dialogue is started. |
|[`onNameNotPresent`](/api/csharp/yarn.unity/dialoguecharacternameview.onnamenotpresent.md)| Invoked when a line is received that doesn't contain a character name. |
|[`onNameUpdate`](/api/csharp/yarn.unity/dialoguecharacternameview.onnameupdate.md)| Invoked when a line is received that contains a character name. The name is given as the parameter. |
## See Also
* [`DialogueUI`](/api/csharp/yarn.unity/dialogueui.md): 
Displays dialogue lines to the player, and sends user choices back
to the dialogue system.

<div class="class-metadata">

Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueCharacterNameView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueCharacterNameView.cs#L26), line 26.
