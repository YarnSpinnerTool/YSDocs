# DialogueViewBase.DialogueComplete()

Method in [DialogueViewBase](/docs/api/csharp/yarn.unity.legacy.dialogueviewbase.md)

## Summary


Called by the  [DialogueRunner](yarn.unity.dialoguerunner.md)  to signal that the
dialogue has ended, and no more lines will be delivered.


```csharp
public virtual void DialogueComplete()
```

## Remarks

<p>This method is called after the last piece of content (that
is, lines, options or commands) finished running.</p> <p>This method is a good place to perform tasks like dismissing
on-screen dialogue UI (for example, turning off a letterboxing
effect, or hiding dialogue UI elements.)
</p> <p>
If [Stop()](yarn.unity.dialoguerunner.stop.md) is called, this method is how your custom views are informed of this.
This allows you to skip over the normal flow of dialogue, so please use this method to clean up your views.
</p> <p>
{% hint style="note" %}
The default implementation of this method does
nothing.
{% endhint %}
</p>

