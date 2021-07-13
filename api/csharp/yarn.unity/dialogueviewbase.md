# DialogueViewBase Class

A <see cref="!:MonoBehaviour"></see> that can present the data of a
dialogue executed by a [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to the user.
The [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) uses subclasses of this type to
relay information to and from the user, and to pause and resume the
execution of the <see cref="!:YarnScript"></see>.


```csharp
public abstract class DialogueViewBase : MonoBehaviour
```
## Remarks

The term "view" is meant in the broadest sense, e.g. a view on the
dialogue (MVVM pattern). Therefore, this abstract class only
defines how a specific view on the dialogue should communicate with
the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) (e.g. display text or trigger a
voice over clip). How to present the content to the user will be
the responsibility of all classes inheriting from this class.

The inheriting classes will receive a [`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md)
and can be in one of the stages defined in <see cref="!:DialogueLineStatus"></see> while presenting it.




## Methods
|Name|Description|
|:---|:---|
|[`DialogueComplete()`](/api/csharp/yarn.unity/dialogueviewbase.dialoguecomplete.md)| Called by the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to signal that the dialogue has ended, and no more lines will be delivered. |
|[`DialogueStarted()`](/api/csharp/yarn.unity/dialogueviewbase.dialoguestarted.md)|Signals that a conversation has started.|
|[`DismissLine(Action)`](/api/csharp/yarn.unity/dialogueviewbase.dismissline-action-.md)| Called by the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to signal that the view should dismiss its current line from display, and clean up. |
|[`MarkLineComplete()`](/api/csharp/yarn.unity/dialogueviewbase.marklinecomplete.md)| Signals that the user wants to go to the next line. |
|[`NodeComplete(String, Action)`](/api/csharp/yarn.unity/dialogueviewbase.nodecomplete-system.string,action-.md)| Called by the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to signal that the end of a node has been reached. |
|[`OnLineStatusChanged(LocalizedLine)`](/api/csharp/yarn.unity/dialogueviewbase.onlinestatuschanged-localizedline-.md)| Called by the DialogueRunner to indicate that the line that this view is delivering has changed state. |
|[`RunLine(LocalizedLine, Action)`](/api/csharp/yarn.unity/dialogueviewbase.runline-localizedline,action-.md)| Called by the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to signal that a line should be displayed to the user. |
|[`RunOptions(DialogueOption[], Action<Int32>)`](/api/csharp/yarn.unity/dialogueviewbase.runoptions-dialogueoption--,action-system.int32--.md)| Called by the [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to signal that a set of options should be displayed to the user. |
## See Also
* [`dialogueViews`](/api/csharp/yarn.unity/dialoguerunner.dialogueviews.md): 
The View classes that will present the dialogue to the user.

* [`DialogueUI`](/api/csharp/yarn.unity/dialogueui.md): 
Displays dialogue lines to the player, and sends user choices back
to the dialogue system.

## Namespace
[`Yarn.Unity`](/api/csharp/yarn.unity/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueViewBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueViewBase.cs#L29), line 29.
