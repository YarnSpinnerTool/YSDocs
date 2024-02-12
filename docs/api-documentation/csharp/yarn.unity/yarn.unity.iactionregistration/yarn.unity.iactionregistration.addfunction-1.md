# AddFunction(string,Delegate)

Method in [IActionRegistration](./)

## Summary

Add a new function that returns a value, so that it can be called from Yarn scripts.

```csharp
void AddFunction(string name, Delegate implementation);
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

| Name                      | Description                                                                |
| ------------------------- | -------------------------------------------------------------------------- |
| `Delegate` implementation | The `System.Delegate` that should be invoked when this function is called. |
| `string` name             |                                                                            |

## See Also

* [Library](../../yarn/yarn.library/): A collection of functions that can be called from Yarn programs.
