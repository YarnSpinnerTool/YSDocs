# YarnTask

Struct in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `System.ValueType`

## Summary



```csharp
public partial struct YarnTask
```

## Methods

|Name|Description|
|:---|:---|
|[Delay(int,CancellationToken)](/docs/api/csharp/yarn.unity.yarntask.delay-2.md)||
|[Delay(TimeSpan,CancellationToken)](/docs/api/csharp/yarn.unity.yarntask.delay-1.md)|Creates a  <a href="yarn.unity.yarntask-1.md">YarnTask</a>  that delays for the time indicated by  <code>timeSpan</code> , and then returns.|
|[Forget()](/docs/api/csharp/yarn.unity.yarntask.forget-1.md)||
|[FromResult(T)](/docs/api/csharp/yarn.unity.yarntask.fromresult-2.md)||
|[GetAwaiter()](/docs/api/csharp/yarn.unity.yarntask.getawaiter-1.md)||
|[IsCompleted()](/docs/api/csharp/yarn.unity.yarntask.iscompleted-1.md)||
|[IsCompletedSuccessfully()](/docs/api/csharp/yarn.unity.yarntask.iscompletedsuccessfully-1.md)||
|[SuppressCancellationThrow()](/docs/api/csharp/yarn.unity.yarntask.suppresscancellationthrow.md)||
|[ToCoroutine(Func<YarnTask>)](/docs/api/csharp/yarn.unity.yarntask.tocoroutine.md)||
|[WaitForAsyncOperation(AsyncOperationHandle,CancellationToken)](/docs/api/csharp/yarn.unity.yarntask.waitforasyncoperation-1.md)||
|[WaitForAsyncOperation(AsyncOperationHandle<T>,CancellationToken)](/docs/api/csharp/yarn.unity.yarntask.waitforasyncoperation-2.md)||
|[WaitUntil(System.Func<bool>,System.Threading.CancellationToken)](/docs/api/csharp/yarn.unity.yarntask.waituntil.md)||
|[WaitUntilCanceled(System.Threading.CancellationToken)](/docs/api/csharp/yarn.unity.yarntask.waituntilcanceled.md)||
|[WhenAll(IEnumerable<YarnTask>)](/docs/api/csharp/yarn.unity.yarntask.whenall-2.md)||
|[WhenAll(YarnTask[])](/docs/api/csharp/yarn.unity.yarntask.whenall-1.md)||
|[WhenAll(IEnumerable<YarnTask<T>>)](/docs/api/csharp/yarn.unity.yarntask.whenall-4.md)||
|[WhenAll(YarnTask<T>[])](/docs/api/csharp/yarn.unity.yarntask.whenall-3.md)||
|[Yield()](/docs/api/csharp/yarn.unity.yarntask.yield.md)||

## Properties

|Name|Description|
|:---|:---|
|[CompletedTask](/docs/api/csharp/yarn.unity.yarntask.completedtask.md)||

## TYPENAME_UNKNOWN_PLURAL

|Name|Description|
|:---|:---|
|[M:Yarn.Unity.YarnTask.op_Implicit(System.Threading.Tasks.Task)~Yarn.Unity.YarnTask](/docs/api/csharp/yarn.unity.yarntask.op_implicit-2.md)||
|[M:Yarn.Unity.YarnTask.op_Implicit(Yarn.Unity.YarnTask)~System.Threading.Tasks.Task](/docs/api/csharp/yarn.unity.yarntask.op_implicit-1.md)||

