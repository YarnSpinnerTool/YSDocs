# Effects.FadeAlpha(CanvasGroup,float,float,float,CoroutineInterruptToken?)

Method in [Effects](/docs/api/csharp/yarn.unity.effects.md)

## Summary


A coroutine that fades a  `UnityEngine.CanvasGroup`  object's opacity
from  `from`  to  `to`  over the
course of  `fadeTime`  seconds, and then invokes  `onComplete` .


```csharp
public static IEnumerator FadeAlpha(CanvasGroup canvasGroup, float from, float to, float fadeTime, CoroutineInterruptToken? stopToken = null)
```

## Parameters

|Name|Description|
|:---|:---|
|`float` from|The opacity value to start fading from, ranging from 0 to 1.|
|`float` to|The opacity value to end fading at, ranging from 0 to 1.|
|[Yarn.Unity.Effects.CoroutineInterruptToken](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.md) stopToken|A  [CoroutineInterruptToken](yarn.unity.effects.coroutineinterrupttoken.md)  that can be used to interrupt the coroutine.|
|`CanvasGroup` canvasGroup||
|`float` fadeTime||

