# FunctionType

Class in [Yarn](yarn.md)

Inherits from `System.Object`

## Summary

A type that represents a function.

```csharp
public class FunctionType : IType
```

## Remarks

Functions have parameters and a return type, and can be called from script. Instances of this type are created when the host application registers new functions (such as through using the [RegisterFunction(string,Delegate)](yarn.library.registerfunction-7.md) methods or similar.)

## Constructors

| Name                                                        | Description |
| ----------------------------------------------------------- | ----------- |
| [FunctionType(IType,IType\[\])](yarn.functiontype..ctor.md) |             |

## Methods

| Name                                         | Description |
| -------------------------------------------- | ----------- |
| [Equals(IType)](yarn.functiontype.equals.md) |             |
| [ToString()](yarn.functiontype.tostring.md)  |             |

## Properties

| Name                                            | Description                                                             |
| ----------------------------------------------- | ----------------------------------------------------------------------- |
| [Description](yarn.functiontype.description.md) | Gets a more verbose description of this type.                           |
| [Name](yarn.functiontype.name.md)               | Gets the name of this type.                                             |
| [Parameters](yarn.functiontype.parameters.md)   | Gets the list of the parameter types that this function is called with. |
| [Parent](yarn.functiontype.parent.md)           | Gets the parent of this type.                                           |
| [ReturnType](yarn.functiontype.returntype.md)   | Gets the type of value that this function returns.                      |
| [TypeMembers](yarn.functiontype.typemembers.md) | Gets the collection of type information for this type's type members.   |
