# Library

Class in [Yarn](yarn.md)

Inherits from `System.Object`

## Summary

A collection of functions that can be called from Yarn programs.

```csharp
public class Library
```

## Remarks

You do not create instances of this class yourself. The [Dialogue](yarn.dialogue.md) class creates one of its own, which you can\
access via the [Library](yarn.dialogue.library.md) property.

## Methods

| Name                                                                                                                            | Description                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DeregisterFunction(string)](yarn.library.deregisterfunction.md)                                                                | Removes a function from the Library.                                                                                                                                                                      |
| [FunctionExists(string)](yarn.library.functionexists.md)                                                                        | Gets a value indicating whether this [Library](yarn.library.md) contains a function named `name` .                                                                                                        |
| [GenerateUniqueVisitedVariableForNode(string)](yarn.library.generateuniquevisitedvariablefornode.md)                            | Generates a unique tracking variable name. This is intended to be used to generate names for visting. Ideally these will very reproduceable and sensible. For now it will be something terrible and easy. |
| [GetFunction(string)](yarn.library.getfunction.md)                                                                              | Returns a `System.Delegate` with a given name.                                                                                                                                                            |
| [ImportLibrary(Library)](yarn.library.importlibrary.md)                                                                         | Loads functions from another [Library](yarn.library.md) .                                                                                                                                                 |
| [RegisterFunction(string,Delegate)](yarn.library.registerfunction-7.md)                                                         | Registers a new function that returns a value, which can be called from a Yarn program.                                                                                                                   |
| [RegisterFunction(string,Func)](yarn.library.registerfunction-1.md)                                                             | Registers a new function that returns a value, which can be called from a Yarn program.                                                                                                                   |
| [RegisterFunction\<T1, TResult>(string,Func\<T1, TResult>)](yarn.library.registerfunction-2.md)                                 | Registers a new function that returns a value, which can be called from a Yarn program.                                                                                                                   |
| [RegisterFunction\<T1, T2, TResult>(string,Func\<T1, T2, TResult>)](yarn.library.registerfunction-3.md)                         | Registers a new function that returns a value, which can be called from a Yarn program.                                                                                                                   |
| [RegisterFunction\<T1, T2, T3, TResult>(string,Func\<T1, T2, T3, TResult>)](yarn.library.registerfunction-4.md)                 | Registers a new function that returns a value, which can be called from a Yarn program.                                                                                                                   |
| [RegisterFunction\<T1, T2, T3, T4, TResult>(string,Func\<T1, T2, T3, T4, TResult>)](yarn.library.registerfunction-5.md)         | Registers a new function that returns a value, which can be called from a Yarn program.                                                                                                                   |
| [RegisterFunction\<T1, T2, T3, T4, T5, TResult>(string,Func\<T1, T2, T3, T4, T5, TResult>)](yarn.library.registerfunction-6.md) | Registers a new function that returns a value, which can be called from a Yarn program.                                                                                                                   |

## See Also

* [Dialogue](yarn.dialogue.md): Co-ordinates the execution of Yarn programs.
