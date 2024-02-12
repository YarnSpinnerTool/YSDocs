# RegisterFunction(string,Delegate)

Method in [Library](./)

## Summary

Registers a new function that returns a value, which can be called from a Yarn program.

```csharp
public void RegisterFunction(string name, Delegate implementation)
```

## Parameters

| Name                             | Description                                           |
| -------------------------------- | ----------------------------------------------------- |
| `string` name                    | The name of the function.                             |
| `System.Delegate` implementation | The method to be invoked when the function is called. |

## Type Parameters

| Name    | Description                      |
| ------- | -------------------------------- |
| TResult | The return type of the function. |
