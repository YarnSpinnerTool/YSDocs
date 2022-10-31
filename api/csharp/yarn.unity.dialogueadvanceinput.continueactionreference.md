# DialogueAdvanceInput.continueActionReference

Field in [DialogueAdvanceInput](api/csharp/yarn.unity.dialogueadvanceinput.md)

## Summary


An  <code>InputActionReference</code>  that refers to the action that
this component is listening for.


```csharp
public InputActionReference continueActionReference = null;
```

## Remarks

<p>
{% hint style="info" %}

This value is only used when <a href="yarn.unity.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is
<a href="yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md">InputSystemActionFromAsset</a>.

{% endhint %}
</p> <p>
Use this continue action type when you want this component to make
use of an input action you've configured elsewhere in your project.
</p>

