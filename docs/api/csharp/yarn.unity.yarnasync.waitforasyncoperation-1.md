# YarnAsync.WaitForAsyncOperation(AsyncOperationHandle<T>,CancellationToken)

Method in [YarnAsync](/docs/api/csharp/yarn.unity.yarnasync.md)

## Summary



```csharp
public static async
#if USE_UNITASK
            UniTask<T?>
#else
            Task<T?>
#endif
        WaitForAsyncOperation<T>(AsyncOperationHandle<T> operationHandle, CancellationToken cancellationToken)
```

## Parameters

|Name|Description|
|:---|:---|
|`UnityEngine.ResourceManagement.AsyncOperations.AsyncOperationHandle<T>` operationHandle||
|`System.Threading.CancellationToken` cancellationToken||

