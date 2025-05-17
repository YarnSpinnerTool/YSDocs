# Effects.Typewriter(TextMeshProUGUI,float,Action,CoroutineInterruptToken?)

Method in [Effects](/docs/api/csharp/yarn.unity.effects.md)

## Summary


A coroutine that gradually reveals the text in a  `TMPro.TextMeshProUGUI`  object over time.


```csharp
public static IEnumerator Typewriter(TextMeshProUGUI text, float lettersPerSecond, Action onCharacterTyped, CoroutineInterruptToken? stopToken = null)
```

## Remarks

<p>This method works by adjusting the value of the `text` parameter's `TMPro.TMP_Text.maxVisibleCharacters` property. This means that
word wrapping will not change half-way through the presentation of a
word.</p> <p>
{% hint style="note" %}
Depending on the value of `lettersPerSecond`, `onCharacterTyped` may
be called multiple times per frame.
{% endhint %}
</p> <p>Due to an internal implementation detail of TextMeshProUGUI,
this method will always take at least one frame to execute,
regardless of the length of the `text` parameter's
text.</p>

## Parameters

|Name|Description|
|:---|:---|
|`TextMeshProUGUI` text|A TextMeshProUGUI object to reveal the text of.|
|`float` lettersPerSecond|The number of letters that should be revealed per second.|
|`Action` onCharacterTyped|An  `System.Action`  that should be called for each character that was revealed.|
|[Yarn.Unity.Effects.CoroutineInterruptToken](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.md) stopToken|A  <a href="yarn.unity.effects.coroutineinterrupttoken.md">CoroutineInterruptToken</a>  that can be used to interrupt the coroutine.|

