# Effects.FadeAlpha(CanvasGroup,float,float,float,CoroutineInterruptToken)

Method in [Effects](/api/csharp/yarn.unity.effects.md)

## Summary


A coroutine that fades a  <code>CanvasGroup</code>  object's opacity
from  <code>from</code>  to  <code>to</code>  over the
course of  <code>fadeTime</code>  seconds, and then invokes  <code>onComplete</code> .


```csharp
public static IEnumerator FadeAlpha(CanvasGroup canvasGroup, float from, float to, float fadeTime, CoroutineInterruptToken stopToken = null)
```

## Parameters

|Name|Description|
|:---|:---|
|`float` from|The opacity value to start fading from, ranging from 0 to 1.|
|`float` to|The opacity value to end fading at, ranging from 0 to 1.|
|[Yarn.Unity.Effects.CoroutineInterruptToken](/api/csharp/yarn.unity.effects.coroutineinterrupttoken.md) stopToken|A  <a href="yarn.unity.effects.coroutineinterrupttoken.md">CoroutineInterruptToken</a>  that can be used to interrupt the coroutine.|
|`CanvasGroup` canvasGroup||
|`float` fadeTime||

