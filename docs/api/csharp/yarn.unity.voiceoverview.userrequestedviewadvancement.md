# UserRequestedViewAdvancement()

Method in [VoiceOverView](yarn.unity.voiceoverview.md)

## Summary

Signals to this dialogue view that the user would like to skip playback.

```csharp
public override void UserRequestedViewAdvancement()
```

## Remarks

When this method is called, this view indicates to its [DialogueRunner](yarn.unity.dialoguerunner.md) that the line should be interrupted.

If this view is not currently playing any audio, this method does nothing.

## See Also

* [DialogueViewBase.InterruptLine(LocalizedLine,Action)](yarn.unity.dialogueviewbase.interruptline.md): Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.
