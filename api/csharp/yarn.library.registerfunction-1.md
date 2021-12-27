# Library.RegisterFunction(string,Func<TResult>)

Method in [Library](/api/csharp/yarn.library.md)

## Summary


Registers a new function that returns a value, which can be
called from a Yarn program.


```csharp
public void RegisterFunction<TResult>(string name, Func<TResult> implementation)
```

## Parameters

|Name|Description|
|:---|:---|
|name|The name of the function.|
|implementation|The  <code>System.Func`1</code>  to be invoked when the function is called.|

## Type Parameters

|Name|Description|
|:---|:---|
|name|The name of the function.|
|implementation|The  <code>System.Func`1</code>  to be invoked when the function is called.|

## Returns



