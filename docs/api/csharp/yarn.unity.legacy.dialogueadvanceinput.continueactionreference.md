# DialogueAdvanceInput.continueActionReference

Field in [DialogueAdvanceInput](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.md)

## Summary


An  <code>UnityEngine.InputSystem.InputActionReference</code>  that refers to the action that
this component is listening for.


```csharp
public InputActionReference? continueActionReference = null;
```

## Remarks

<p>
{% hint style="info" %}

This value is only used when <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is
<a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md">InputSystemActionFromAsset</a>.

{% endhint %}
</p> <p>
Use this continue action type when you want this component to make
use of an input action you've configured elsewhere in your project.
</p>

