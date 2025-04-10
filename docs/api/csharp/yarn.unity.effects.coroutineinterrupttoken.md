# CoroutineInterruptToken

Class in [Effects](yarn.unity.effects.md)

Inherits from `System.Object`

## Summary

An object that can be used to signal to a coroutine that it should terminate early.

```csharp
public class CoroutineInterruptToken
```

## Remarks

While coroutines can be stopped by calling `UnityEngine.MonoBehaviour.StopCoroutine(System.Collections.IEnumerator)` or `UnityEngine.MonoBehaviour.StopAllCoroutines`, this has the side effect of also stopping any coroutine that was waiting for the now-stopped coroutine to finish.

Instances of this class may be passed as a parameter to a coroutine that they can periodically poll to see if they should terminate earlier than planned.

To use this class, create an instance of it, and pass it as a parameter to your coroutine. In the coroutine, call [Start()](yarn.unity.effects.coroutineinterrupttoken.start.md) to mark that the coroutine is running. During the coroutine's execution, periodically check the [WasInterrupted](yarn.unity.effects.coroutineinterrupttoken.wasinterrupted.md) property to determine if the coroutine should exit. If it is `true`, the coroutine should exit (via the `yield break` statement.) At the normal exit of your coroutine, call the [Complete()](yarn.unity.effects.coroutineinterrupttoken.complete.md) method to mark that the coroutine is no longer running. To make a coroutine stop, call the [Interrupt()](yarn.unity.effects.coroutineinterrupttoken.interrupt.md) method.

You can also use the [CanInterrupt](yarn.unity.effects.coroutineinterrupttoken.caninterrupt.md) property to determine if the token is in a state in which it can stop (that is, a coroutine that's using it is currently running.)

## Methods

| Name                                                                   | Description |
| ---------------------------------------------------------------------- | ----------- |
| [Complete()](yarn.unity.effects.coroutineinterrupttoken.complete.md)   |             |
| [Interrupt()](yarn.unity.effects.coroutineinterrupttoken.interrupt.md) |             |
| [Start()](yarn.unity.effects.coroutineinterrupttoken.start.md)         |             |

## Properties

| Name                                                                           | Description |
| ------------------------------------------------------------------------------ | ----------- |
| [CanInterrupt](yarn.unity.effects.coroutineinterrupttoken.caninterrupt.md)     |             |
| [WasInterrupted](yarn.unity.effects.coroutineinterrupttoken.wasinterrupted.md) |             |
