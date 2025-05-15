# FunctionTypeBuilder

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Provides methods for constructing  [FunctionType](yarn.functiontype.md) 
objects.


```csharp
public class FunctionTypeBuilder
```

## Remarks


To use this class, create an instance of it, and call the
`With` -prefixed methods to set properties. When you're done, access
the  [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md)  property to get the final, constructed
[FunctionType](yarn.functiontype.md) .


## Methods

|Name|Description|
|:---|:---|
|[FromFunctionType(System.Type)](/docs/api/csharp/yarn.compiler.functiontypebuilder.fromfunctiontype.md)|Creates a new  [FunctionTypeBuilder](yarn.compiler.functiontypebuilder.md)  based on a delegate type.|
|[WithParameter(IType)](/docs/api/csharp/yarn.compiler.functiontypebuilder.withparameter.md)|Adds a new parameter of type  `parameterType`  to the [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md) .|
|[WithReturnType(IType)](/docs/api/csharp/yarn.compiler.functiontypebuilder.withreturntype.md)|Sets the  [FunctionType](yarn.functiontype.returntype.md">ReturnType</a>  of the  <a href="yarn.compiler.functiontypebuilder.functiontype.md) .|
|[WithVariadicParameterType(IType?)](/docs/api/csharp/yarn.compiler.functiontypebuilder.withvariadicparametertype.md)|Sets the  [VariadicParameterType](yarn.functiontype.variadicparametertype.md)  of the [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md) .|

## Properties

|Name|Description|
|:---|:---|
|[FunctionType](/docs/api/csharp/yarn.compiler.functiontypebuilder.functiontype.md)|Gets the  [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md)  instance constructed by this [FunctionTypeBuilder](yarn.compiler.functiontypebuilder.md) .|

