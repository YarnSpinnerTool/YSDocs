# DialogueAdvanceInput.continueActionOnButtonRelease

Field in [DialogueAdvanceInput](/docs/api/csharp/yarn.unity.dialogueadvanceinput.md)

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

This value is only used when <a href="yarn.unity.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> is
<a href="yarn.unity.dialogueadvanceinput.continueactiontype.keycode.md">KeyCode</a> or <a href="yarn.unity.dialogueadvanceinput.continueactiontype.virtualbutton.md">VirtualButton</a>.

{% endhint %}
</p>

