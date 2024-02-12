# dialogueView

Field in [DialogueAdvanceInput](./)

## Summary

The dialogue view that will be notified when the user performs the advance input (as configured by [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) and related fields.)

```csharp
public DialogueViewBase dialogueView;
```

## Remarks

When the input is performed, this dialogue view will have its [UserRequestedViewAdvancement()](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.userrequestedviewadvancement.md) method called.
