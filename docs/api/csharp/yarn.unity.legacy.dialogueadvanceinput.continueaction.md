# DialogueAdvanceInput.continueAction

Field in [DialogueAdvanceInput](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.md)

## Summary


The  <code>UnityEngine.InputSystem.InputAction</code>  that this component is listening for.


```csharp
public InputAction continueAction = new InputAction("Skip", InputActionType.Button, CommonUsages.Submit);
```

## Remarks

<p>
{% hint style="info" %}

This value is only used when <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is
<a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemaction.md">InputSystemAction</a>.

{% endhint %}
</p> <p>
Use this continue action type when you want this component to use a
configurable input action, but don't want to have to set up other
actions in your project.
</p>

