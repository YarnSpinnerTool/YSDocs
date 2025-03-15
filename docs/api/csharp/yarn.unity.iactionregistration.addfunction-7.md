# AddFunction(string,System.Func\<T1, T2, T3, T4, T5, TResult>)

Method in [IActionRegistration](yarn.unity.iactionregistration.md)

## Summary

Add a new function that returns a value, so that it can be called from Yarn scripts.

```csharp
void AddFunction<T1, T2, T3, T4, T5, TResult>(string name, System.Func<T1, T2, T3, T4, T5, TResult> implementation);
```

## Remarks

When this function has been registered, it can be called from your Yarn scripts like so:

```
<<if myFunction(1, 2) == true>>
myFunction returned true!
<<endif>>
```

The `call` command can also be used to invoke the function:

```
<<call myFunction(1, 2)>>
```

## Parameters

| Name                                               | Description                                                                |
| -------------------------------------------------- | -------------------------------------------------------------------------- |
| `Func<T1, T2, T3, T4, T5, TResult>` implementation | The `System.Delegate` that should be invoked when this function is called. |
| `string` name                                      |                                                                            |

## Type Parameters

| Name    | Description                                            |
| ------- | ------------------------------------------------------ |
| TResult | The type of the value that the function should return. |
| T1      | The type of the first parameter to the function.       |
| T2      | The type of the second parameter to the function.      |
| T3      | The type of the third parameter to the function.       |
| T4      | The type of the fourth parameter to the function.      |
| T5      | The type of the fifth parameter to the function.       |

## See Also

* [Library](yarn.library.md): A collection of functions that can be called from Yarn programs.
