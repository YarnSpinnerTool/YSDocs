# YarnFunctionAttribute

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from [`YarnActionAttribute`](/api/csharp/yarn.unity.yarnactionattribute.md)

## Summary


Marks the method as a function to be registered with the running
instance's library.


```csharp
public class YarnFunctionAttribute : YarnActionAttribute
```

## Remarks


See  <code>Library.RegisterFunction(string, Delegate)</code>  and the
generic overloads for what is and is not valid.

This will throw an error if you attempt to add a function that has
more than 16 parameters, as that is the largest overload that
<code>Func&lt;TResult&gt;</code>  etc has.


## Properties

|Name|Description|
|:---|:---|
|[FunctionName](/api/csharp/yarn.unity.yarnfunctionattribute.functionname.md)||

