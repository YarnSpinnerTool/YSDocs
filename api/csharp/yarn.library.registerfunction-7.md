# Library.RegisterFunction(string,Delegate)

Method in [Library](/api/csharp/yarn.library.md)

## Summary


Registers a new function that returns a value, which can be
called from a Yarn program.


```csharp
public void RegisterFunction(string name, Delegate implementation)
```

## Parameters

|Name|Description|
|:---|:---|
|name|The name of the function.|
|implementation|The  <code>System.Func`1</code>  to be invoked when the function is called.|
|name|The name of the function.|
|implementation|The  <code>System.Delegate</code>  that should be invoked when this function is called from Yarn scripts.|

## Type Parameters

|Name|Description|
|:---|:---|
|name|The name of the function.|
|implementation|The  <code>System.Func`1</code>  to be invoked when the function is called.|
|name|The name of the function.|
|implementation|The  <code>System.Delegate</code>  that should be invoked when this function is called from Yarn scripts.|

## Returns



