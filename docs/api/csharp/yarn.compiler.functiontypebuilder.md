# FunctionTypeBuilder

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Provides methods for constructing  <a href="yarn.functiontype.md">FunctionType</a> 
objects.


```csharp
public class FunctionTypeBuilder
```

## Remarks


To use this class, create an instance of it, and call the
<code>With</code> -prefixed methods to set properties. When you're done, access
the  <a href="yarn.compiler.functiontypebuilder.functiontype.md">FunctionType</a>  property to get the final, constructed
<a href="yarn.functiontype.md">FunctionType</a> .


## Methods

|Name|Description|
|:---|:---|
|[FromFunctionType(System.Type)](/docs/api/csharp/yarn.compiler.functiontypebuilder.fromfunctiontype.md)|Creates a new  <a href="yarn.compiler.functiontypebuilder.md">FunctionTypeBuilder</a>  based on a delegate type.|
|[WithParameter(IType)](/docs/api/csharp/yarn.compiler.functiontypebuilder.withparameter.md)|Adds a new parameter of type  <code>parameterType</code>  to the <a href="yarn.compiler.functiontypebuilder.functiontype.md">FunctionType</a> .|
|[WithReturnType(IType)](/docs/api/csharp/yarn.compiler.functiontypebuilder.withreturntype.md)|Sets the  <a href="yarn.functiontype.returntype.md">ReturnType</a>  of the  <a href="yarn.compiler.functiontypebuilder.functiontype.md">FunctionType</a> .|
|[WithVariadicParameterType(IType?)](/docs/api/csharp/yarn.compiler.functiontypebuilder.withvariadicparametertype.md)|Sets the  <a href="yarn.functiontype.variadicparametertype.md">VariadicParameterType</a>  of the <a href="yarn.compiler.functiontypebuilder.functiontype.md">FunctionType</a> .|

## Properties

|Name|Description|
|:---|:---|
|[FunctionType](/docs/api/csharp/yarn.compiler.functiontypebuilder.functiontype.md)|Gets the  <a href="yarn.compiler.functiontypebuilder.functiontype.md">FunctionType</a>  instance constructed by this <a href="yarn.compiler.functiontypebuilder.md">FunctionTypeBuilder</a> .|

