# DialogueViewBase

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `MonoBehaviour`

## Summary


A  <code>MonoBehaviour</code>  that can present the data of a
dialogue executed by a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to the user.
The  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  uses subclasses of this type to
relay information to and from the user, and to pause and resume the
execution of the  <code>YarnScript</code> .


```csharp
public abstract class DialogueViewBase : MonoBehaviour
    {
    }
```

## Remarks


The term "view" is meant in the broadest sense, e.g. a view on the
dialogue (MVVM pattern). Therefore, this abstract class only
defines how a specific view on the dialogue should communicate with
the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  (e.g. display text or trigger a
voice over clip). How to present the content to the user will be
the responsibility of all classes inheriting from this class.

The inheriting classes will receive a  <a href="yarn.unity.localizedline.md">LocalizedLine</a> 
and can be in one of the stages defined in  <code>DialogueLineStatus</code>  while presenting it.


## See Also

* [dialogueViews](/api/csharp/yarn.unity.dialoguerunner.dialogueviews.md)
* DialogueUI

## Methods

|Name|Description|
|:---|:---|
|[DialogueStarted()](/api/csharp/yarn.unity.dialogueviewbase.dialoguestarted.md)|Signals that a conversation has started.|
|[RunLine(LocalizedLine,Action)](/api/csharp/yarn.unity.dialogueviewbase.runline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.|
|[OnLineStatusChanged(LocalizedLine)](/api/csharp/yarn.unity.dialogueviewbase.onlinestatuschanged.md)|Called by the DialogueRunner to indicate that the line that this view is delivering has changed state.|
|[DismissLine(Action)](/api/csharp/yarn.unity.dialogueviewbase.dismissline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.|
|[RunOptions(DialogueOption[],Action<int>)](/api/csharp/yarn.unity.dialogueviewbase.runoptions.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.|
|[NodeComplete(string,Action)](/api/csharp/yarn.unity.dialogueviewbase.nodecomplete.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the end of a node has been reached.|
|[DialogueComplete()](/api/csharp/yarn.unity.dialogueviewbase.dialoguecomplete.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[ReadyForNextLine()](/api/csharp/yarn.unity.dialogueviewbase.readyfornextline.md)|Signals that the user wants to go to the next line.|

