# Action

Property in [DialogueAdvanceInput](yarn.unity.dialogueadvanceinput.md)

## Summary

Gets the `UnityEngine.InputSystem.InputAction` configured by this [DialogueAdvanceInput](yarn.unity.dialogueadvanceinput.md) .

```csharp
public InputAction Action
{
            get; }
```

## Remarks

This methods returns the following potential values:

* If [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) is [InputSystemAction](yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemaction.md), this method returns [continueAction](yarn.unity.dialogueadvanceinput.continueaction.md).
* If [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) is [InputSystemActionFromAsset](yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md), this method returns [continueActionReference](yarn.unity.dialogueadvanceinput.continueactionreference.md)'s action.
* If [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) is [KeyCode](yarn.unity.dialogueadvanceinput.continueactiontype.keycode.md) or [None](yarn.unity.dialogueadvanceinput.continueactiontype.none.md), this method returns `null`.
