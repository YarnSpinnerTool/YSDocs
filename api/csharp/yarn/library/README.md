# Library

A collection of functions that can be called from Yarn programs.

```csharp
public class Library
```

## Remarks

You do not create instances of this class yourself. The [`Dialogue`](../dialogue/) class creates one of its own, which you can access via the [`Library`](../dialogue/dialogue.library.md) property.

## Methods

| Name | Description |
| :--- | :--- |
| [`DeregisterFunction(String)`](library.deregisterfunction-system.string.md) | Removes a function from the Library. |
| [`FunctionExists(String)`](library.functionexists-system.string.md) | Gets a value indicating whether this [`Library`](./) contains a function named `name`. |
| [`GetFunction(String)`](library.getfunction-system.string.md) | Returns a [`Delegate`](https://docs.microsoft.com/dotnet/api/System.Delegate) with a given name. |
| [`ImportLibrary(Library)`](library.importlibrary-library.md) | Loads functions from another [`Library`](./). |
| [`RegisterFunction(String, Delegate)`](library.registerfunction-system.string-system.delegate.md) |  |
| [`RegisterFunction<TResult>(String, Func<TResult>)`](library.registerfunction-1-system.string-system.func-0.md) | Registers a new function that returns a value, which can be called from a Yarn program. |
| [`RegisterFunction<T1, TResult>(String, Func<T1, TResult>)`](library.registerfunction-2-system.string-system.func-0-1.md) |  |
| [`RegisterFunction<T1, T2, TResult>(String, Func<T1, T2, TResult>)`](library.registerfunction-3-system.string-system.func-0-1-2.md) |  |
| [`RegisterFunction<T1, T2, T3, TResult>(String, Func<T1, T2, T3, TResult>)`](library.registerfunction-4-system.string-system.func-0-1-2-3.md) |  |
| [`RegisterFunction<T1, T2, T3, T4, TResult>(String, Func<T1, T2, T3, T4, TResult>)`](library.registerfunction-5-system.string-system.func-0-1-2-3-4.md) |  |
| [`RegisterFunction<T1, T2, T3, T4, T5, TResult>(String, Func<T1, T2, T3, T4, T5, TResult>)`](library.registerfunction-6-system.string-system.func-0-1-2-3-4-5.md) |  |

## See Also

* [`Dialogue`](../dialogue/): 

  Co-ordinates the execution of Yarn programs.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Library.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Library.cs#L16), line 16.

