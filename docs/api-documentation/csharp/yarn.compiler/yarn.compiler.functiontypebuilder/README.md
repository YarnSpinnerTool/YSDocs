# FunctionTypeBuilder

Class in [Yarn.Compiler](../)

Inherits from `System.Object`

## Summary

Provides methods for constructing [FunctionType](../../yarn/yarn.functiontype/) objects.

```csharp
public class FunctionTypeBuilder
```

## Remarks

To use this class, create an instance of it, and call the `With` -prefixed methods to set properties. When you're done, access the [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md) property to get the final, constructed [FunctionType](../../yarn/yarn.functiontype/) .

## Methods

| Name                                                                         | Description                                                                                                                                                    |
| ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [WithParameter(IType)](yarn.compiler.functiontypebuilder.withparameter.md)   | Adds a new parameter of type `parameterType` to the [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md) .                                        |
| [WithReturnType(IType)](yarn.compiler.functiontypebuilder.withreturntype.md) | Sets the [ReturnType](../../yarn/yarn.functiontype/yarn.functiontype.returntype.md) of the [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md) . |

## Properties

| Name                                                              | Description                                                                                                                         |
| ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md) | Gets the [FunctionType](yarn.compiler.functiontypebuilder.functiontype.md) instance constructed by this [FunctionTypeBuilder](./) . |
