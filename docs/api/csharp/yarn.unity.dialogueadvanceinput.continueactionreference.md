# continueActionReference

Field in [DialogueAdvanceInput](yarn.unity.dialogueadvanceinput.md)

## Summary

An `UnityEngine.InputSystem.InputActionReference` that refers to the action that this component is listening for.

```csharp
public InputActionReference continueActionReference = null;
```

## Remarks

{% hint style="info" %}
This value is only used when [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) is [InputSystemActionFromAsset](yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md).
{% endhint %}

Use this continue action type when you want this component to make use of an input action you've configured elsewhere in your project.
