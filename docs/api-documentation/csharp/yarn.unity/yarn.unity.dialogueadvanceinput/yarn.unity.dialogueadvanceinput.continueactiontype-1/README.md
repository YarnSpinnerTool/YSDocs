# ContinueActionType

Enum in [DialogueAdvanceInput](../)

Inherits from `System.Enum`

## Summary

The type of input that this component is listening for in order to signal that its dialogue view should advance.

```csharp
public enum ContinueActionType
{
    None,
    KeyCode,
    InputSystemAction,
    InputSystemActionFromAsset
}
```

## Members

| Name                                                                                                           | Description                                                                                                                                                           |
| -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [InputSystemAction](yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemaction.md)                   | The component is listening for the action configured in [continueAction](../yarn.unity.dialogueadvanceinput.continueaction.md) to be performed.                       |
| [InputSystemActionFromAsset](yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md) | The component is listening for the action referred to by [continueActionReference](../yarn.unity.dialogueadvanceinput.continueactionreference.md) to be performed.    |
| [KeyCode](yarn.unity.dialogueadvanceinput.continueactiontype.keycode.md)                                       | The component is listening for a key on the keyboard to be pressed.                                                                                                   |
| [None](yarn.unity.dialogueadvanceinput.continueactiontype.none.md)                                             | The component is listening for no input. This component will not signal to [dialogueView](../yarn.unity.dialogueadvanceinput.dialogueview.md) that it should advance. |
