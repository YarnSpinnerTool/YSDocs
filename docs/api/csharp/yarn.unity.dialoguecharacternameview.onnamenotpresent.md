# onNameNotPresent

Field in [DialogueCharacterNameView](yarn.unity.dialoguecharacternameview.md)

## Summary

Invoked when a line is received that doesn't contain a character name.

```csharp
public UnityEvent onNameNotPresent;
```

## Remarks

Games can use this event to hide the name UI.

## See Also

* [DialogueCharacterNameView.onNameUpdate](yarn.unity.dialoguecharacternameview.onnameupdate.md): Invoked when a line is received that contains a character name. The name is given as the parameter.
