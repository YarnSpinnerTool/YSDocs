# Effects

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary


Contains coroutine methods that apply visual effects. This class is used
by  `LineView`  to handle animating the presentation of lines.


```csharp
public static class Effects
```

## Classes

|Name|Description|
|:---|:---|
|[CoroutineInterruptToken](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.md)|An object that can be used to signal to a coroutine that it should terminate early.|

## Methods

|Name|Description|
|:---|:---|
|[FadeAlpha(CanvasGroup,float,float,float,CancellationToken)](/docs/api/csharp/yarn.unity.effects.fadealpha-2.md)||
|[FadeAlpha(CanvasGroup,float,float,float,CoroutineInterruptToken?)](/docs/api/csharp/yarn.unity.effects.fadealpha-1.md)|A coroutine that fades a  `UnityEngine.CanvasGroup`  object's opacity from  `from`  to  `to`  over the course of  `fadeTime`  seconds, and then invokes  `onComplete` .|
|[FadeAlphaAsync(CanvasGroup,float,float,float,CancellationToken)](/docs/api/csharp/yarn.unity.effects.fadealphaasync.md)||
|[PausableTypewriter(TextMeshProUGUI,float,Action?,Action?,Action?,Stack<(int position, float duration)>?,CoroutineInterruptToken?)](/docs/api/csharp/yarn.unity.effects.pausabletypewriter.md)|A coroutine that gradually reveals the text in a  `TMPro.TextMeshProUGUI`  object over time.|
|[Typewriter(TextMeshProUGUI,float,Action,CoroutineInterruptToken?)](/docs/api/csharp/yarn.unity.effects.typewriter.md)|A coroutine that gradually reveals the text in a  `TMPro.TextMeshProUGUI`  object over time.|

