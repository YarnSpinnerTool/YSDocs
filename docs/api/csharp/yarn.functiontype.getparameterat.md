# GetParameterAt(int)

Method in [FunctionType](yarn.functiontype.md)

## Summary

Gets the type of the parameter at the given index.

```csharp
public IType GetParameterAt(int index)
```

## Parameters

| Name        | Description                                     |
| ----------- | ----------------------------------------------- |
| `int` index | The index of the parameter to get the type for. |

## Returns

The type of the parameter. If `index` is\
beyond the length of [Parameters](yarn.functiontype.parameters.md) , and [VariadicParameterType](yarn.functiontype.variadicparametertype.md) is not `null` , [VariadicParameterType](yarn.functiontype.variadicparametertype.md) is returned.
