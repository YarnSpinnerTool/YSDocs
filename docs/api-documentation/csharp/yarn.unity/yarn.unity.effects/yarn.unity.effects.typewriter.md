# Typewriter(TextMeshProUGUI,float,Action,CoroutineInterruptToken)

Method in [Effects](./)

## Summary

A coroutine that gradually reveals the text in a `TMPro.TextMeshProUGUI` object over time.

```csharp
public static IEnumerator Typewriter(TextMeshProUGUI text, float lettersPerSecond, Action onCharacterTyped, CoroutineInterruptToken stopToken = null)
```

## Remarks

This method works by adjusting the value of the `text` parameter's `TextMeshProUGUI.maxVisibleCharacters` property. This means that word wrapping will not change half-way through the presentation of a word.

{% hint style="info" %}
Depending on the value of `lettersPerSecond`, `onCharacterTyped` may be called multiple times per frame.
{% endhint %}

Due to an internal implementation detail of TextMeshProUGUI, this method will always take at least one frame to execute, regardless of the length of the `text` parameter's text.

## Parameters

| Name                                                                                                | Description                                                                                                           |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `TMPro.TextMeshProUGUI` text                                                                        | A TextMeshProUGUI object to reveal the text of.                                                                       |
| `float` lettersPerSecond                                                                            | The number of letters that should be revealed per second.                                                             |
| `System.Action` onCharacterTyped                                                                    | An `System.Action` that should be called for each character that was revealed.                                        |
| [Yarn.Unity.Effects.CoroutineInterruptToken](yarn.unity.effects.coroutineinterrupttoken/) stopToken | A [CoroutineInterruptToken](yarn.unity.effects.coroutineinterrupttoken/) that can be used to interrupt the coroutine. |
