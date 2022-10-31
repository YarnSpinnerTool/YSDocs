# DialogueAdvanceInput.dialogueView

Field in [DialogueAdvanceInput](api/csharp/yarn.unity.dialogueadvanceinput.md)

## Summary


The dialogue view that will be notified when the user performs the
advance input (as configured by  <a href="yarn.unity.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a>  and
related fields.)


```csharp
public DialogueViewBase dialogueView;
```

## Remarks


When the input is performed, this dialogue view will have its  <a href="yarn.unity.dialogueviewbase.userrequestedviewadvancement.md">UserRequestedViewAdvancement()</a>  method
called.


