# DialogueAdvanceInput.Action

Property in [DialogueAdvanceInput](/api/csharp/yarn.unity.dialogueadvanceinput.md)

## Summary


Gets the  <code>UnityEngine.InputSystem.InputAction</code>  configured by this  <a href="yarn.unity.dialogueadvanceinput.md">DialogueAdvanceInput</a> .


```csharp
public InputAction Action
{
            get; }
```

## Remarks

<p>
This methods returns the following potential values:
</p> <ul type="bullet">
<li>
If <a href="yarn.unity.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemaction.md">InputSystemAction</a>, this method returns
<a href="yarn.unity.dialogueadvanceinput.continueaction.md">continueAction</a>.
</li>
<li>
If <a href="yarn.unity.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md">InputSystemActionFromAsset</a>, this method
returns <a href="yarn.unity.dialogueadvanceinput.continueactionreference.md">continueActionReference</a>'s action.
</li>
<li>
If <a href="yarn.unity.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.dialogueadvanceinput.continueactiontype.keycode.md">KeyCode</a> or <a href="yarn.unity.dialogueadvanceinput.continueactiontype.none.md">None</a>, this method returns <code>null</code>.
</li>
</ul>

