# RunLine(LocalizedLine,Action)

Method in [LineView](./)

## Summary

Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line should be displayed to the user.

```csharp
public override void RunLine(LocalizedLine dialogueLine, Action onDialogueLineFinished)
```

## Remarks

When this method is called, the Dialogue View should present the line to the user. The content to present is contained within the `dialogueLine` parameter, which contains information about the line in the user's current locale.

{% hint style="info" %}
The value of the `dialogueLine` parameter is produced by the Dialogue Runner's [LineProviderBehaviour](../yarn.unity.lineproviderbehaviour/).
{% endhint %}

It's up to the Dialogue View to decide what "presenting" the line may mean; for example, showing on-screen text, or playing voice-over audio.

When the line has finished being presented, this method calls the `onDialogueLineFinished` method, which signals to the Dialogue Runner that this Dialogue View has finished presenting the line. When all Dialogue Views have finished presenting the line, the Dialogue Runner calls [DismissLine(Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.dismissline.md) to signal that the views should get rid of the line.

If you want to create a Dialogue View that waits for user input before continuing, either wait for that input before calling `onDialogueLineFinished`, or don't call it at all and instead call [requestInterrupt](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.requestinterrupt.md) to tell the Dialogue Runner to interrupt the line.

{% hint style="danger" %}
The `onDialogueLineFinished` method should only be called when [RunLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.runline.md) finishes its presentation normally. If [InterruptLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.interruptline.md) has been called, you must call the completion handler that it receives, and not the completion handler that [RunLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.runline.md) has received.
{% endhint %}

{% hint style="info" %}
The default implementation of this method immediately calls the `onDialogueLineFinished` method (that is, it reports that it has finished presenting the line the moment that it receives it), and otherwise does nothing.
{% endhint %}

## Parameters

| Name                                                                  | Description                                                                   |
| --------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [Yarn.Unity.LocalizedLine](../yarn.unity.localizedline/) dialogueLine | The content of the line that should be presented to the user.                 |
| `System.Action` onDialogueLineFinished                                | The method that should be called after the line has finished being presented. |

## See Also

* [DialogueViewBase.InterruptLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.interruptline.md): Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.
* [DialogueViewBase.DismissLine(Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.dismissline.md): Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that the view should dismiss its current line from display, and clean up.
* [DialogueViewBase.RunOptions(DialogueOption\[\],Action\<int>)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.runoptions.md): Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a set of options should be displayed to the user.
