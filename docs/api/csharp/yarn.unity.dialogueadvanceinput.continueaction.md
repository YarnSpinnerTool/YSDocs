# continueAction

Field in [DialogueAdvanceInput](yarn.unity.dialogueadvanceinput.md)

## Summary

The `UnityEngine.InputSystem.InputAction` that this component is listening for.

```csharp
public InputAction continueAction = new InputAction("Skip", InputActionType.Button, CommonUsages.Submit);
```

## Remarks

{% hint style="info" %}
This value is only used when [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) is [InputSystemAction](yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemaction.md).
{% endhint %}

Use this continue action type when you want this component to use a configurable input action, but don't want to have to set up other actions in your project.
