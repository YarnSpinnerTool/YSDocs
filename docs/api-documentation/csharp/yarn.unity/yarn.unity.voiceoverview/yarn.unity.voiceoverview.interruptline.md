# InterruptLine(LocalizedLine,Action)

Method in [VoiceOverView](./)

## Summary

Interrupts the playback of the specified line, and quickly fades the playback to silent.

```csharp
public override void InterruptLine(LocalizedLine dialogueLine, Action onDialogueLineFinished)
```

## Remarks

{% hint style="warning" %}
This method is not intended to be called from your code. Instead, the [DialogueRunner](../yarn.unity.dialoguerunner/) class will call it at the appropriate time.
{% endhint %}

## Parameters

| Name                                                                  | Description                                                                   |
| --------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [Yarn.Unity.LocalizedLine](../yarn.unity.localizedline/) dialogueLine | The current line that is being presented.                                     |
| `System.Action` onDialogueLineFinished                                | The method that should be called after the line has finished being presented. |

## See Also

* [DialogueViewBase.InterruptLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.interruptline.md): Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.
