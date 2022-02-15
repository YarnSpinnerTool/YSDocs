# ContinueActionType

Enum in [DialogueAdvanceInput](/api/csharp/yarn.unity.dialogueadvanceinput.md)

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

|Name|Description|
|:---|:---|
|[InputSystemAction](/api/csharp/yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemaction.md)|The component is listening for the action configured in  <a href="yarn.unity.dialogueadvanceinput.continueaction.md">continueAction</a>  to be performed.|
|[InputSystemActionFromAsset](/api/csharp/yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md)|The component is listening for the action referred to by  <a href="yarn.unity.dialogueadvanceinput.continueactionreference.md">continueActionReference</a>  to be performed.|
|[KeyCode](/api/csharp/yarn.unity.dialogueadvanceinput.continueactiontype.keycode.md)|The component is listening for a key on the keyboard to be pressed.|
|[None](/api/csharp/yarn.unity.dialogueadvanceinput.continueactiontype.none.md)|The component is listening for no input. This component will not signal to  <a href="yarn.unity.dialogueadvanceinput.dialogueview.md">dialogueView</a>  that it should advance.|

