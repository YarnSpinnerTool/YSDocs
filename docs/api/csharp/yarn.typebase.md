# TypeBase

Class in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


Provides the base class for all concrete types.


```csharp
public abstract class TypeBase : IType, IEquatable<TypeBase>
```

## Methods

|Name|Description|
|:---|:---|
|[Equals(object)](/docs/api/csharp/yarn.typebase.equals-2.md)||
|[Equals(TypeBase)](/docs/api/csharp/yarn.typebase.equals-1.md)||
|[GetHashCode()](/docs/api/csharp/yarn.typebase.gethashcode.md)||
|[IsAncestorOf(TypeBase)](/docs/api/csharp/yarn.typebase.isancestorof.md)|Gets whether this type is an ancestor of  `other` .|
|[IsConvertibleTo(TypeBase)](/docs/api/csharp/yarn.typebase.isconvertibleto.md)|Checks if this type is convertible to the type represented by `otherType` .|
|[ToString()](/docs/api/csharp/yarn.typebase.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[ConvertibleToTypes](/docs/api/csharp/yarn.typebase.convertibletotypes.md)|Gets the collection of types that this type may be converted to.|
|[Description](/docs/api/csharp/yarn.typebase.description.md)|Gets a string describing this type.|
|[Methods](/docs/api/csharp/yarn.typebase.methods.md)|Gets the collection of methods that are defined on this type.|
|[Name](/docs/api/csharp/yarn.typebase.name.md)|Gets the name of this type.|
|[Parent](/docs/api/csharp/yarn.typebase.parent.md)|Gets the parent of this type.|
|[TypeMembers](/docs/api/csharp/yarn.typebase.typemembers.md)|Gets a dictionary containing the members of this type.|

