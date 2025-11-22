# AddFunction\<T1, TResult>(IActionRegistration,string,System.Func\<T1, TResult>)

Method in [ActionRegistrationExtension](yarn.unity.actionregistrationextension.md)

## Summary

Add a new function that returns a value, so that it can be called\
from Yarn scripts.

```csharp
public static void AddFunction<T1, TResult>(this IActionRegistration registration, string name, System.Func<T1, TResult> implementation);
```

## Remarks

When this function has been registered, it can be called from\
your Yarn scripts like so:

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

| Name                                                                             | Description                                                                |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `string` name                                                                    | The name of the function to add.                                           |
| `Func<T1, TResult>` implementation                                               | The `System.Delegate` that should be invoked when this function is called. |
| [Yarn.Unity.IActionRegistration](yarn.unity.iactionregistration.md) registration |                                                                            |

## Type Parameters

| Name    | Description                 |
| ------- | --------------------------- |
| TResult | The result of the function. |

## See Also

* [Library](yarn.library.md): A collection of functions that can be called from Yarn programs.
