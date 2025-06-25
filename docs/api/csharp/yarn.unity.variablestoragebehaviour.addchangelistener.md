# AddChangeListener\<T>(string,Action\<T>)

Method in [VariableStorageBehaviour](yarn.unity.variablestoragebehaviour.md)

## Summary

Registers a delegate that will be called when the variable `variableName` is modified.

```csharp
public IDisposable AddChangeListener<T>(string variableName, Action<T> onChange)
```

## Parameters

| Name                  | Description                                                                                                                |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `string` variableName | The name of the variable to watch for changes to. This variable must be of type `T` , and it must not be a smart variable. |
| `Action<T>` onChange  | The delegate to run when the variable changes value.                                                                       |

## Type Parameters

| Name | Description               |
| ---- | ------------------------- |
| T    | The type of the variable. |

## Returns

An `System.IDisposable` that removes the registration\
when its `System.IDisposable.Dispose` method is\
called.
