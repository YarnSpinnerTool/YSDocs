# FunctionType

Class in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


A type that represents a function.


```csharp
public class FunctionType : IType
```

## Remarks


Functions have parameters and a return type, and can be called from
script. Instances of this type are created when the host
application registers new functions (such as through using the  <a href="yarn.library.registerfunction-7.md">RegisterFunction(string,Delegate)</a>  methods or similar.)


## Constructors

|Name|Description|
|:---|:---|
|[FunctionType(IType,IType[])](/docs/api/csharp/yarn.functiontype..ctor.md)||

## Methods

|Name|Description|
|:---|:---|
|[Equals(IType)](/docs/api/csharp/yarn.functiontype.equals.md)||
|[ToString()](/docs/api/csharp/yarn.functiontype.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[Description](/docs/api/csharp/yarn.functiontype.description.md)|Gets a more verbose description of this type.|
|[Name](/docs/api/csharp/yarn.functiontype.name.md)|Gets the name of this type.|
|[Parameters](/docs/api/csharp/yarn.functiontype.parameters.md)|Gets the list of the parameter types that this function is called with.|
|[Parent](/docs/api/csharp/yarn.functiontype.parent.md)|Gets the parent of this type.|
|[ReturnType](/docs/api/csharp/yarn.functiontype.returntype.md)|Gets the type of value that this function returns.|
|[TypeMembers](/docs/api/csharp/yarn.functiontype.typemembers.md)|Gets the collection of type information for this type's type members.|

