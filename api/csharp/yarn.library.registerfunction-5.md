# RegisterFunction(string,Func<T1, T2, T3, T4, TResult>)

Method in [Library](/api/csharp/yarn.library.md)

## Summary


Registers a new function that returns a value, which can be
called from a Yarn program.


```csharp
public void RegisterFunction<T1, T2, T3, T4, TResult>(string name, Func<T1, T2, T3, T4, TResult> implementation)
```

## Parameters

|Name|Description|
|:---|:---|
|name|The name of the function.|
|implementation|The  <code>T:System.Func`1</code>  to be invoked when the function is called.|

## Type Parameters

|Name|Description|
|:---|:---|
|name|The name of the function.|
|implementation|The  <code>T:System.Func`1</code>  to be invoked when the function is called.|

## Returns



