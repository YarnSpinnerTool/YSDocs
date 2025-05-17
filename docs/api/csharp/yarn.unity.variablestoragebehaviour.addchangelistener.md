# VariableStorageBehaviour.AddChangeListener(string,Action<T>)

Method in [VariableStorageBehaviour](/docs/api/csharp/yarn.unity.variablestoragebehaviour.md)

## Summary


Registers a delegate that will be called when the variable  <code>variableName</code>  is modified. 


```csharp
public IDisposable AddChangeListener<T>(string variableName, Action<T> onChange)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` variableName|The name of the variable to watch for changes to. This variable must be of type  <code>T</code> , and it must not be a smart variable.|
|`Action<T>` onChange|The delegate to run when the variable changes value.|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of the variable.|

## Returns

An  <code>System.IDisposable</code>  that removes the registration
when its  <code>System.IDisposable.Dispose</code>  method is
called.

