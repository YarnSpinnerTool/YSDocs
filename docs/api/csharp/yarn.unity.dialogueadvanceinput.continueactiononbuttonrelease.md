# continueActionOnButtonRelease

Field in [DialogueAdvanceInput](yarn.unity.dialogueadvanceinput.md)

## Summary

Should the continue action respond to key being pressed down or released.

```csharp
public ContinueButtonActionType continueActionOnButtonRelease = ContinueButtonActionType.Up;
```

## Remarks

{% hint style="info" %}
Defaults to firing the advancement on key released.
{% endhint %}

{% hint style="info" %}
This value is only used when [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) is [KeyCode](yarn.unity.dialogueadvanceinput.continueactiontype.keycode.md) or [VirtualButton](yarn.unity.dialogueadvanceinput.continueactiontype.virtualbutton.md).
{% endhint %}
