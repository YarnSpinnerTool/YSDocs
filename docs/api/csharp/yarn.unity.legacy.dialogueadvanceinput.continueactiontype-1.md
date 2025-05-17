# ContinueActionType

Enum in [DialogueAdvanceInput](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.md)

Inherits from `System.Enum`

## Summary


The type of input that this component is listening for in order to signal that its dialogue view should advance.


```csharp
public enum ContinueActionType
{
    None,
    KeyCode,
    VirtualButton,
    InputSystemAction,
    InputSystemActionFromAsset
}
```

## Members

|Name|Description|
|:---|:---|
|[InputSystemAction](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemaction.md)|The component is listening for the action configured in  <a href="yarn.unity.legacy.dialogueadvanceinput.continueaction.md">continueAction</a>  to be performed.|
|[InputSystemActionFromAsset](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md)|The component is listening for the action referred to by  <a href="yarn.unity.legacy.dialogueadvanceinput.continueactionreference.md">continueActionReference</a>  to be performed.|
|[KeyCode](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactiontype.keycode.md)|The component is listening for a key on the keyboard to be pressed.|
|[None](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactiontype.none.md)|The component is listening for no input. This component will not signal to  <a href="yarn.unity.legacy.dialogueadvanceinput.dialogueview.md">dialogueView</a>  that it should advance.|
|[VirtualButton](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactiontype.virtualbutton.md)|The component is listening for a virtual button to be pressed.|

