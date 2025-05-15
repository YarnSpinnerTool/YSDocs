# Effects.PausableTypewriter(TextMeshProUGUI,float,Action?,Action?,Action?,Stack<(int position, float duration)>?,CoroutineInterruptToken?)

Method in [Effects](/docs/api/csharp/yarn.unity.effects.md)

## Summary


A coroutine that gradually reveals the text in a  `TMPro.TextMeshProUGUI`  object over time.


```csharp
public static IEnumerator PausableTypewriter(TextMeshProUGUI text, float lettersPerSecond, Action? onCharacterTyped, Action? onPauseStarted, Action? onPauseEnded, Stack<(int position, float duration)>? pausePositions, CoroutineInterruptToken? stopToken = null)
```

## Remarks


Essentially identical to  [Typewriter(TextMeshProUGUI,float,Action,CoroutineInterruptToken?)](yarn.unity.effects.typewriter.md)  but
supports pausing the animation based on  `pausePositions`  values.
<p>This method works by adjusting the value of the `text` parameter's `TMPro.TMP_Text.maxVisibleCharacters` property. This means
that word wrapping will not change half-way through the presentation
of a word.</p> <p>
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
|`TextMeshProUGUI` text|A TextMeshProUGUI object to reveal the text of|
|`float` lettersPerSecond|The number of letters that should be revealed per second.|
|`Action` onCharacterTyped|An  `System.Action`  that should be called for each character that was revealed.|
|`Action` onPauseStarted|An  `System.Action`  that will be called when the typewriter effect is paused.|
|`Action` onPauseEnded|An  `System.Action`  that will be called when the typewriter effect is restarted.|
|`Stack<(int position, float duration)>` pausePositions|A stack of character position and pause duration tuples used to pause the effect. Generally created by  `LineView.GetPauseDurationsInsideLine`|
|[Yarn.Unity.Effects.CoroutineInterruptToken](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.md) stopToken|A  [CoroutineInterruptToken](yarn.unity.effects.coroutineinterrupttoken.md)  that can be used to interrupt the coroutine.|

