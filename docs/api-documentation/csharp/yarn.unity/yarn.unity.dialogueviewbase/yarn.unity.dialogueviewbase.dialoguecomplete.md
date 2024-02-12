# DialogueComplete()

Method in [DialogueViewBase](./)

## Summary

Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that the dialogue has ended, and no more lines will be delivered.

```csharp
public virtual void DialogueComplete()
```

## Remarks

This method is called after the last piece of content (that is, lines, options or commands) finished running.

This method is a good place to perform tasks like dismissing on-screen dialogue UI (for example, turning off a letterboxing effect, or hiding dialogue UI elements.)

If [Stop()](../yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.stop.md) is called, this method is how your custom views are informed of this. This allows you to skip over the normal flow of dialogue, so please use this method to clean up your views.

{% hint style="info" %}
The default implementation of this method does nothing.
{% endhint %}
