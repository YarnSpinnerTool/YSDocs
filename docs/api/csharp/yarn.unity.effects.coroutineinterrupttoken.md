# CoroutineInterruptToken

Class in [Effects](/api/csharp/yarn.unity.effects.md)

Inherits from `System.Object`

## Summary


An object that can be used to signal to a coroutine that it should
terminate early.


```csharp
public class CoroutineInterruptToken
```

## Remarks

<p>
While coroutines can be stopped by calling <code>UnityEngine.MonoBehaviour.StopCoroutine(System.Collections.IEnumerator)</code> or <code>UnityEngine.MonoBehaviour.StopAllCoroutines</code>, this has the side effect
of also stopping any coroutine that was waiting for the now-stopped
coroutine to finish.
</p> <p>
Instances of this class may be passed as a parameter to a coroutine
that they can periodically poll to see if they should terminate
earlier than planned.
</p> <p>
To use this class, create an instance of it, and pass it as a
parameter to your coroutine. In the coroutine, call <a href="yarn.unity.effects.coroutineinterrupttoken.start.md">Start()</a> to mark that the coroutine is running. During the
coroutine's execution, periodically check the <a href="yarn.unity.effects.coroutineinterrupttoken.wasinterrupted.md">WasInterrupted</a> property to determine if the coroutine
should exit. If it is <code>true</code>, the coroutine should
exit (via the <code>yield break</code> statement.) At the normal exit of
your coroutine, call the <a href="yarn.unity.effects.coroutineinterrupttoken.complete.md">Complete()</a> method to mark that the
coroutine is no longer running. To make a coroutine stop, call the
<a href="yarn.unity.effects.coroutineinterrupttoken.interrupt.md">Interrupt()</a> method.
</p> <p>
You can also use the <a href="yarn.unity.effects.coroutineinterrupttoken.caninterrupt.md">CanInterrupt</a> property to
determine if the token is in a state in which it can stop (that is,
a coroutine that's using it is currently running.)
</p>

## Methods

|Name|Description|
|:---|:---|
|[Complete()](/api/csharp/yarn.unity.effects.coroutineinterrupttoken.complete.md)||
|[Interrupt()](/api/csharp/yarn.unity.effects.coroutineinterrupttoken.interrupt.md)||
|[Start()](/api/csharp/yarn.unity.effects.coroutineinterrupttoken.start.md)||

## Properties

|Name|Description|
|:---|:---|
|[CanInterrupt](/api/csharp/yarn.unity.effects.coroutineinterrupttoken.caninterrupt.md)||
|[WasInterrupted](/api/csharp/yarn.unity.effects.coroutineinterrupttoken.wasinterrupted.md)||

