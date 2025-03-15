# RunLine(LocalizedLine,Action)

Method in [VoiceOverView](yarn.unity.voiceoverview.md)

## Summary

Begins playing the associated audio for the specified line.

```csharp
public override void RunLine(LocalizedLine dialogueLine, Action onDialogueLineFinished)
```

## Remarks

{% hint style="warning" %}
This method is not intended to be called from your code. Instead, the [DialogueRunner](yarn.unity.dialoguerunner.md) class will call it at the appropriate time.
{% endhint %}

## Parameters

| Name                                                                 | Description                                                                   |
| -------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [Yarn.Unity.LocalizedLine](yarn.unity.localizedline.md) dialogueLine | The content of the line that should be presented to the user.                 |
| `Action` onDialogueLineFinished                                      | The method that should be called after the line has finished being presented. |

## See Also

* [DialogueViewBase.RunLine(LocalizedLine,Action)](yarn.unity.dialogueviewbase.runline.md): Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line should be displayed to the user.
