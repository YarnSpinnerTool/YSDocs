# FadeAlpha(CanvasGroup,float,float,float,Action,InterruptionFlag)

Method in [Effects](/api/csharp/yarn.unity.effects.md)

## Summary


A coroutine that fades a  <code>CanvasGroup</code>  object's
opacity from  <code>from</code>  to  <code>to</code> 
over the course of  <code>fadeTime</code>  seconds, and then
invokes  <code>onComplete</code> . An  <a href="yarn.unity.interruptionflag.md">InterruptionFlag</a>  may be used to signal that the fade
should be interrupted; if this happens, the opacity is set to
<code>to</code> .


```csharp
public static IEnumerator FadeAlpha(CanvasGroup canvasGroup, float from, float to, float fadeTime, Action onComplete = null, InterruptionFlag interruption = null)
```

## Parameters

|Name|Description|
|:---|:---|
|from|The opacity value to start fading from, ranging from 0 to 1.|
|to|The opacity value to end fading at, ranging from 0 to 1.|
|onComplete|A delegate to invoke after fading is complete.|
|canvasGroup||
|fadeTime||
|interruption||

## Returns



