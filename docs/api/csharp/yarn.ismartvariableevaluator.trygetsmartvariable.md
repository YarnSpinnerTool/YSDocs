# TryGetSmartVariable(string,T)

Method in [ISmartVariableEvaluator](yarn.ismartvariableevaluator.md)

## Summary

Evaluate the value of a smart variable named `name` .

```csharp
bool TryGetSmartVariable<T>(string name, out T result);
```

## Parameters

| Name          | Description                                                                                                                                                                                      |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `string` name | The name of the variable.                                                                                                                                                                        |
| `T` result    | On return, contains the returned value of the smart variable, or the `default` value of `T` if a smart variable named `name` could not be found or its value could not be returned as type `T` . |

## Type Parameters

| Name | Description                     |
| ---- | ------------------------------- |
| T    | The type of the returned value. |

## Returns

`true` if the smart variable was evaluated, `false` otherwise.
