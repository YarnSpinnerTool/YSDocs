# Library

Class in [Yarn](/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


A collection of functions that can be called from Yarn programs.


```csharp
public class Library
```

## Remarks


You do not create instances of this class yourself. The  <a href="yarn.dialogue.md">Dialogue</a>  class creates one of its own, which you can
access via the  <a href="yarn.dialogue.library.md">Library</a>  property.


## Methods

|Name|Description|
|:---|:---|
|[DeregisterFunction(string)](/api/csharp/yarn.library.deregisterfunction.md)|Removes a function from the Library.|
|[FunctionExists(string)](/api/csharp/yarn.library.functionexists.md)|Gets a value indicating whether this  <a href="yarn.library.md">Library</a>  contains a function named  <code>name</code> .|
|[GenerateUniqueVisitedVariableForNode(string)](/api/csharp/yarn.library.generateuniquevisitedvariablefornode.md)|Generates a unique tracking variable name. This is intended to be used to generate names for visting. Ideally these will very reproduceable and sensible. For now it will be something terrible and easy.|
|[GetFunction(string)](/api/csharp/yarn.library.getfunction.md)|Returns a  <code>System.Delegate</code>  with a given name.|
|[ImportLibrary(Library)](/api/csharp/yarn.library.importlibrary.md)|Loads functions from another  <a href="yarn.library.md">Library</a> .|
|[RegisterFunction(string,Delegate)](/api/csharp/yarn.library.registerfunction-7.md)|Registers a new function that returns a value, which can be called from a Yarn program.|
|[RegisterFunction(string,Func<TResult>)](/api/csharp/yarn.library.registerfunction-1.md)|Registers a new function that returns a value, which can be called from a Yarn program.|
|[RegisterFunction(string,Func<T1, TResult>)](/api/csharp/yarn.library.registerfunction-2.md)|Registers a new function that returns a value, which can be called from a Yarn program.|
|[RegisterFunction(string,Func<T1, T2, TResult>)](/api/csharp/yarn.library.registerfunction-3.md)|Registers a new function that returns a value, which can be called from a Yarn program.|
|[RegisterFunction(string,Func<T1, T2, T3, TResult>)](/api/csharp/yarn.library.registerfunction-4.md)|Registers a new function that returns a value, which can be called from a Yarn program.|
|[RegisterFunction(string,Func<T1, T2, T3, T4, TResult>)](/api/csharp/yarn.library.registerfunction-5.md)|Registers a new function that returns a value, which can be called from a Yarn program.|
|[RegisterFunction(string,Func<T1, T2, T3, T4, T5, TResult>)](/api/csharp/yarn.library.registerfunction-6.md)|Registers a new function that returns a value, which can be called from a Yarn program.|

## See Also

* [Dialogue](/api/csharp/yarn.dialogue.md): Co-ordinates the execution of Yarn programs.

