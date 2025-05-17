# DialogueAdvanceInput.continueActionOnButtonRelease

Field in [DialogueAdvanceInput](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.md)

## Summary


Should the continue action respond to key being pressed down or released.


```csharp
public ContinueButtonActionType continueActionOnButtonRelease = ContinueButtonActionType.Up;
```

## Remarks

<p>
{% hint style="info" %}

Defaults to firing the advancement on key released.

{% endhint %}
</p> <p>
{% hint style="info" %}

This value is only used when [continueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md) is
[VirtualButton](yarn.unity.legacy.dialogueadvanceinput.continueactiontype.keycode.md">KeyCode</a> or <a href="yarn.unity.legacy.dialogueadvanceinput.continueactiontype.virtualbutton.md).

{% endhint %}
</p>

