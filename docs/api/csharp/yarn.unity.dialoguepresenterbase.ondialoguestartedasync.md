# DialoguePresenterBase.OnDialogueStartedAsync()

Method in [DialoguePresenterBase](/docs/api/csharp/yarn.unity.dialoguepresenterbase.md)

## Summary

Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that
dialogue has started.

```csharp
public abstract YarnTask OnDialogueStartedAsync();
```

## Remarks

<p>This method is called before any content (that is, lines,
options or commands) are delivered.</p> <p>This method is a good place to perform tasks like preparing
on-screen dialogue UI (for example, turning on a letterboxing
effect, or making dialogue UI elements visible.)
</p> <p>
{% hint style="note" %}
The default implementation of this method does
nothing.
{% endhint %}
</p>

## Returns

A task that represents any work done by this dialogue view in order to get ready for dialogue to run.

