# VariableStorageBehaviour.AddChangeListener(System.Action<string, object>)

Method in [VariableStorageBehaviour](/docs/api/csharp/yarn.unity.variablestoragebehaviour.md)

## Summary


Registers a delegate that will be called when any variable is modified. 


```csharp
public IDisposable AddChangeListener(System.Action<string, object> onChange)
```

## Parameters

|Name|Description|
|:---|:---|
|`Action<string, object>` onChange|The delegate to run when the variable changes value.|

## Returns

An  <code>System.IDisposable</code>  that removes the registration
when its  <code>System.IDisposable.Dispose</code>  method is
called.

