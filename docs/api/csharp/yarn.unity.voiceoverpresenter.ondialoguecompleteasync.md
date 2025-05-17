# VoiceOverPresenter.OnDialogueCompleteAsync()

Method in [VoiceOverPresenter](/docs/api/csharp/yarn.unity.voiceoverpresenter.md)

## Summary


Called by the  [DialogueRunner](yarn.unity.dialoguerunner.md)  to signal that the
dialogue has ended, and no more lines will be delivered.


```csharp
public override YarnTask OnDialogueCompleteAsync()
```

## Remarks

<p>This method is called after the last piece of content (that
is, lines, options or commands) finished running.</p> <p>This method is a good place to perform tasks like dismissing
on-screen dialogue UI (for example, turning off a letterboxing
effect, or hiding dialogue UI elements.)
</p> <p>
{% hint style="note" %}
The default implementation of this method does
nothing.
{% endhint %}
</p>

## Returns

A task that represents any work done by this dialogue view
in order to clean up after running dialogue.

