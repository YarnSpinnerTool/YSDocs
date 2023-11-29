# Effects

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary


Contains coroutine methods that apply visual effects. This class is used
by  <a href="yarn.unity.lineview.md">LineView</a>  to handle animating the presentation of lines.


```csharp
public static class Effects
```

## Classes

|Name|Description|
|:---|:---|
|[CoroutineInterruptToken](/api/csharp/yarn.unity.effects.coroutineinterrupttoken.md)|An object that can be used to signal to a coroutine that it should terminate early.|

## Methods

|Name|Description|
|:---|:---|
|[FadeAlpha(CanvasGroup,float,float,float,CoroutineInterruptToken)](/api/csharp/yarn.unity.effects.fadealpha.md)|A coroutine that fades a  <code>UnityEngine.CanvasGroup</code>  object's opacity from  <code>from</code>  to  <code>to</code>  over the course of  <code>fadeTime</code>  seconds, and then invokes  <code>onComplete</code> .|
|[PausableTypewriter(TextMeshProUGUI,float,Action,Action,Action,Stack<(int position, float duration)>,CoroutineInterruptToken)](/api/csharp/yarn.unity.effects.pausabletypewriter.md)|A coroutine that gradually reveals the text in a  <code>TMPro.TextMeshProUGUI</code>  object over time.|
|[Typewriter(TextMeshProUGUI,float,Action,CoroutineInterruptToken)](/api/csharp/yarn.unity.effects.typewriter.md)|A coroutine that gradually reveals the text in a  <code>TMPro.TextMeshProUGUI</code>  object over time.|

