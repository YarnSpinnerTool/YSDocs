# Effects.FadeAlpha(CanvasGroup,float,float,float,PresentationFlag,Action)

Method in [Effects](/api/csharp/yarn.unity.effects.md)

## Summary


A coroutine that fades a  <code>CanvasGroup</code>  object's
opacity from  <code>from</code>  to  <code>to</code> 
over the course of  <code>fadeTime</code>  seconds, and then
invokes  <code>onComplete</code> .


```csharp
public static IEnumerator FadeAlpha(CanvasGroup canvasGroup, float from, float to, float fadeTime, PresentationFlag presented = null, Action onComplete = null)
```

## Parameters

|Name|Description|
|:---|:---|
|`float` from|The opacity value to start fading from, ranging from 0 to 1.|
|`float` to|The opacity value to end fading at, ranging from 0 to 1.|
|`Action` onComplete|A delegate to invoke after fading is complete.|
|`CanvasGroup` canvasGroup||
|`float` fadeTime||
|[Yarn.Unity.PresentationFlag](/api/csharp/yarn.unity.presentationflag.md) presented||

