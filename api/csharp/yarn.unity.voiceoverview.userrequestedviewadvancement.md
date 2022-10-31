# VoiceOverView.UserRequestedViewAdvancement()

Method in [VoiceOverView](/api/csharp/yarn.unity.voiceoverview.md)

## Summary


Signals to this dialogue view that the user would like to skip
playback.


```csharp
public override void UserRequestedViewAdvancement()
```

## Remarks

<p>
When this method is called, this view indicates to its <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> that the line should be interrupted.
</p> <p>
If this view is not currently playing any audio, this method does
nothing.
</p>

## See Also

* [DialogueViewBase.InterruptLine\(LocalizedLine,Action\)](/api/csharp/yarn.unity.dialogueviewbase.interruptline.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.

