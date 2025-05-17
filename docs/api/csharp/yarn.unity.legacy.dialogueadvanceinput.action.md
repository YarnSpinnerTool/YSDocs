# DialogueAdvanceInput.Action

Property in [DialogueAdvanceInput](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.md)

## Summary


Gets the  `UnityEngine.InputSystem.InputAction`  configured by this  [DialogueAdvanceInput](yarn.unity.legacy.dialogueadvanceinput.md) .


```csharp
public InputAction? Action
{
            get; }
```

## Remarks

<p>
This methods returns the following potential values:
</p> <ul type="bullet">
<li>
If [InputSystemAction](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemaction.md), this method returns
[continueAction](yarn.unity.legacy.dialogueadvanceinput.continueaction.md).
</li>
<li>
If [InputSystemActionFromAsset](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md), this method
returns [continueActionReference](yarn.unity.legacy.dialogueadvanceinput.continueactionreference.md)'s action.
</li>
<li>
If [None](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.keycode.md">KeyCode</a> or <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.none.md), this method returns `null`.
</li>
</ul>

