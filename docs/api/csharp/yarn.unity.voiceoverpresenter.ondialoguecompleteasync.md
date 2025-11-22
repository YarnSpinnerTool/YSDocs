# OnDialogueCompleteAsync()

Method in [VoiceOverPresenter](yarn.unity.voiceoverpresenter.md)

## Summary

Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that the\
dialogue has ended, and no more lines will be delivered.

```csharp
public override YarnTask OnDialogueCompleteAsync()
```

## Remarks

This method is called after the last piece of content (that\
is, lines, options or commands) finished running.

This method is a good place to perform tasks like dismissing\
on-screen dialogue UI (for example, turning off a letterboxing\
effect, or hiding dialogue UI elements.)

{% hint style="info" %}
The default implementation of this method does\
nothing.
{% endhint %}

## Returns

A task that represents any work done by this dialogue presenter\
in order to clean up after running dialogue.
