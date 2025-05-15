# CoroutineInterruptToken

Class in [Effects](/docs/api/csharp/yarn.unity.effects.md)

Inherits from `System.Object`

## Summary


An object that can be used to signal to a coroutine that it should
terminate early.


```csharp
public class CoroutineInterruptToken
```

## Remarks

<p>
While coroutines can be stopped by calling `UnityEngine.MonoBehaviour.StopCoroutine(System.Collections.IEnumerator)` or `UnityEngine.MonoBehaviour.StopAllCoroutines`, this has the side effect
of also stopping any coroutine that was waiting for the now-stopped
coroutine to finish.
</p> <p>
Instances of this class may be passed as a parameter to a coroutine
that they can periodically poll to see if they should terminate
earlier than planned.
</p> <p>
To use this class, create an instance of it, and pass it as a
parameter to your coroutine. In the coroutine, call [Start()](yarn.unity.effects.coroutineinterrupttoken.start.md) to mark that the coroutine is running. During the
coroutine's execution, periodically check the [WasInterrupted](yarn.unity.effects.coroutineinterrupttoken.wasinterrupted.md) property to determine if the coroutine
should exit. If it is `true`, the coroutine should
exit (via the `yield break` statement.) At the normal exit of
your coroutine, call the [Complete()](yarn.unity.effects.coroutineinterrupttoken.complete.md) method to mark that
the coroutine is no longer running. To make a coroutine stop, call
the [Interrupt()](yarn.unity.effects.coroutineinterrupttoken.interrupt.md) method.
</p> <p>
You can also use the [CanInterrupt](yarn.unity.effects.coroutineinterrupttoken.caninterrupt.md) property to
determine if the token is in a state in which it can stop (that is,
a coroutine that's using it is currently running.)
</p>

## Methods

|Name|Description|
|:---|:---|
|[Complete()](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.complete.md)||
|[Interrupt()](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.interrupt.md)||
|[Start()](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.start.md)||

## Properties

|Name|Description|
|:---|:---|
|[CanInterrupt](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.caninterrupt.md)||
|[WasInterrupted](/docs/api/csharp/yarn.unity.effects.coroutineinterrupttoken.wasinterrupted.md)||

