# DialogueAdvanceInput.Action

Property in [DialogueAdvanceInput](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.md)

## Summary


Gets the  `UnityEngine.InputSystem.InputAction`  configured by this  <a href="yarn.unity.legacy.dialogueadvanceinput.md">DialogueAdvanceInput</a> .


```csharp
public InputAction? Action { get; }
```

## Remarks

<p>
This methods returns the following potential values:
</p> <ul type="bullet">
<li>
If <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemaction.md">InputSystemAction</a>, this method returns
<a href="yarn.unity.legacy.dialogueadvanceinput.continueaction.md">continueAction</a>.
</li>
<li>
If <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.inputsystemactionfromasset.md">InputSystemActionFromAsset</a>, this method
returns <a href="yarn.unity.legacy.dialogueadvanceinput.continueactionreference.md">continueActionReference</a>'s action.
</li>
<li>
If <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.keycode.md">KeyCode</a> or <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.none.md">None</a>, this method returns `null`.
</li>
</ul>

