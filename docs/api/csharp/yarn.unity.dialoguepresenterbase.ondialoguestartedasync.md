# OnDialogueStartedAsync()

Method in [DialoguePresenterBase](yarn.unity.dialoguepresenterbase.md)

## Summary

Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that\
dialogue has started.

```csharp
public abstract YarnTask OnDialogueStartedAsync();
```

## Remarks

This method is called before any content (that is, lines,\
options or commands) are delivered.

This method is a good place to perform tasks like preparing\
on-screen dialogue UI (for example, turning on a letterboxing\
effect, or making dialogue UI elements visible.)

{% hint style="info" %}
The default implementation of this method does\
nothing.
{% endhint %}

## Returns

A task that represents any work done by this dialogue presenter in order to get ready for dialogue to run.
