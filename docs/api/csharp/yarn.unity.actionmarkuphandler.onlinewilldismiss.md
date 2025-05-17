# ActionMarkupHandler.OnLineWillDismiss()

Method in [ActionMarkupHandler](/docs/api/csharp/yarn.unity.actionmarkuphandler.md)

## Summary


Called right before the line will dismiss itself.


```csharp
public abstract void OnLineWillDismiss();
```

## Remarks


This does not mean that the entirety of the view itself will have been removed, just the  <a href="yarn.unity.dialoguepresenterbase.md">DialoguePresenterBase</a>  has completed displaying everything and is returning control back to the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to let more content flow.


