# Action

Property in [DialogueAdvanceInput](yarn.unity.legacy.dialogueadvanceinput.md)

## Summary

Gets the `UnityEngine.InputSystem.InputAction` configured by this [DialogueAdvanceInput](yarn.unity.legacy.dialogueadvanceinput.md) .

```csharp
public InputAction? Action { get; }
```

## Remarks

This methods returns the following potential values:

* If [continueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md) is [InputSystemAction](yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemaction.md), this method returns[continueAction](yarn.unity.legacy.dialogueadvanceinput.continueaction.md).
* If [continueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md) is [InputSystemActionFromAsset](yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md), this method\
  returns [continueActionReference](yarn.unity.legacy.dialogueadvanceinput.continueactionreference.md)'s action.
* If [continueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md) is [KeyCode](yarn.unity.legacy.dialogueadvanceinput.continueactiontype.keycode.md) or [None](yarn.unity.legacy.dialogueadvanceinput.continueactiontype.none.md), this method returns `null`.
