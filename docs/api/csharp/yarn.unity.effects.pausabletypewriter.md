# Effects.PausableTypewriter(TextMeshProUGUI,float,Action,Action,Action,Stack<(int position, float duration)>,CoroutineInterruptToken)

Method in [Effects](/docs/api/csharp/yarn.unity.effects.md)

## Summary


A coroutine that gradually reveals the text in a  <code>TMPro.TextMeshProUGUI</code>  object over time.


```csharp
public static IEnumerator PausableTypewriter(TextMeshProUGUI text, float lettersPerSecond, Action onCharacterTyped, Action onPauseStarted, Action onPauseEnded, Stack<(int position, float duration)> pausePositions, CoroutineInterruptToken stopToken = null)
```

## Remarks


Essentially identical to  <a href="yarn.unity.effects.typewriter.md">Typewriter(TextMeshProUGUI,float,Action,CoroutineInterruptToken)</a>  but supports pausing the animation based on  <code>pausePositions</code>  values.
<p>This method works by adjusting the value of the <code>text</code> parameter's <code>TextMeshProUGUI.maxVisibleCharacters</code> property. This means that word wrapping will not change half-way through the presentation of a word.</p> <p>
{% hint style="note" %}
Depending on the value of <code>lettersPerSecond</code>, <code>onCharacterTyped</code> may be called multiple times per frame.
{% endhint %}
</p> <p>Due to an internal implementation detail of TextMeshProUGUI, this method will always take at least one frame to execute, regardless of the length of the <code>text</code> parameter's text.</p>

## Parameters

|Name|Description|
|:---|:---|
|`TextMeshProUGUI` text|A TextMeshProUGUI object to reveal the text of|
|`float` lettersPerSecond|The number of letters that should be revealed per second.|
|`Action` onCharacterTyped|An  <code>System.Action</code>  that should be called for each character that was revealed.|
|`Action` onPauseStarted|An  <code>System.Action</code>  that will be called when the typewriter effect is paused.|
|`Action` onPauseEnded|An  <code>System.Action</code>  that will be called when the typewriter effect is restarted.|
|`Stack<(int position, float duration)>` pausePositions|A stack of character position and pause duration tuples used to pause the effect. Generally created by  <a href="yarn.unity.lineview.getpausedurationsinsideline.md">GetPauseDurationsInsideLine(Markup.MarkupParseResult)</a>|
|[Yarn.Unity.Effects.CoroutineInterruptToken](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.md) stopToken|A  <a href="yarn.unity.effects.coroutineinterrupttoken.md">CoroutineInterruptToken</a>  that can be used to interrupt the coroutine.|

