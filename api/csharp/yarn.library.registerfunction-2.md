# Library.RegisterFunction(string,Func<T1, TResult>)

Method in [Library](api/csharp/yarn.library.md)

## Summary


Registers a new function that returns a value, which can be
called from a Yarn program.


```csharp
public void RegisterFunction<T1, TResult>(string name, Func<T1, TResult> implementation)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the function.|
|`System.Func<T1, TResult>` implementation|The method to be invoked when the function is called.|

## Type Parameters

|Name|Description|
|:---|:---|
|TResult|The return type of the function.|
|TResult|The return type of the function.|
|T1|The type of the function's first argument.|

