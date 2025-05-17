# FunctionType.GetParameterAt(int)

Method in [FunctionType](/docs/api/csharp/yarn.functiontype.md)

## Summary


Gets the type of the parameter at the given index.


```csharp
public IType GetParameterAt(int index)
```

## Parameters

|Name|Description|
|:---|:---|
|`int` index|The index of the parameter to get the type for.|

## Returns

The type of the parameter. If  <code>index</code>  is
beyond the length of  <a href="yarn.functiontype.parameters.md">Parameters</a> , and  <a href="yarn.functiontype.variadicparametertype.md">VariadicParameterType</a>  is not  <code>null</code> ,  <a href="yarn.functiontype.variadicparametertype.md">VariadicParameterType</a>  is returned. 

