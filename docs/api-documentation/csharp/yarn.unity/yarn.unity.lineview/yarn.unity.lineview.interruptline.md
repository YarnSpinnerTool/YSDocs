# InterruptLine(LocalizedLine,Action)

Method in [LineView](./)

## Summary

Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.

```csharp
public override void InterruptLine(LocalizedLine dialogueLine, Action onInterruptLineFinished)
```

## Remarks

This method is called when Dialogue Runner wants to interrupt the presentation of the current line, in order to proceed to the next piece of content.

When this method is called, the Dialogue View must finish presenting their line as quickly as it can. Depending on how this Dialogue View presents lines, this can mean different things: for example, a view that plays voice-over audio might stop playback immediately, or fade out playback over a short period of time; a view that displays text a letter at a time might display all of the text at once.

The process of finishing the presentation can take time to complete, but should happen as quickly as possible, because this method is generally called when the user wants to skip the current line.

When the line has finished presenting, the `onDialogueLineFinished` method must be called, which indicates to the Dialogue Runner that this line is ready to be dismissed.

{% hint style="danger" %}
When [InterruptLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.interruptline.md) is called, you must not call the completion handler that [RunLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.runline.md) has previously received - this completion handler is no longer valid. Call this method's `onDialogueLineFinished` instead.
{% endhint %}

{% hint style="info" %}
The default implementation of this method immediately calls the `onDialogueLineFinished` method (that is, it reports that it has finished presenting the line the moment that it receives it), and otherwise does nothing.
{% endhint %}

## Parameters

| Name                                                                  | Description                                                                   |
| --------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [Yarn.Unity.LocalizedLine](../yarn.unity.localizedline/) dialogueLine | The current line that is being presented.                                     |
| onDialogueLineFinished                                                | The method that should be called after the line has finished being presented. |
| `System.Action` onInterruptLineFinished                               |                                                                               |

## See Also

* [DialogueViewBase.RunLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.runline.md): Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line should be displayed to the user.
* [DialogueViewBase.DismissLine(Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.dismissline.md): Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that the view should dismiss its current line from display, and clean up.
