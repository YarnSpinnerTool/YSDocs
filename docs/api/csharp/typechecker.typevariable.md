# TypeVariable

Class in [TypeChecker](/docs/api/csharp/typechecker.md)

Inherits from `System.Object`

## Summary


A type variable represents a type that is not yet known.


```csharp
public class TypeVariable : IType, IEquatable<TypeVariable>
```

## Constructors

|Name|Description|
|:---|:---|
|[TypeVariable(string,Antlr4.Runtime.ParserRuleContext)](/docs/api/csharp/typechecker.typevariable..ctor.md)|Initialises a new  [TypeVariable](typechecker.typevariable.md) .|

## Methods

|Name|Description|
|:---|:---|
|[Equals(object)](/docs/api/csharp/typechecker.typevariable.equals-1.md)||
|[Equals(TypeVariable)](/docs/api/csharp/typechecker.typevariable.equals-3.md)||
|[Equals(IType)](/docs/api/csharp/typechecker.typevariable.equals-2.md)||
|[GetHashCode()](/docs/api/csharp/typechecker.typevariable.gethashcode.md)||
|[ToString()](/docs/api/csharp/typechecker.typevariable.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[Context](/docs/api/csharp/typechecker.typevariable.context.md)|Gets the parser context associated with this type (that is, the expression or other parse context whose type is represented by this type variable.)|
|[Description](/docs/api/csharp/typechecker.typevariable.description.md)|Gets a more verbose description of this type.|
|[Name](/docs/api/csharp/typechecker.typevariable.name.md)|Gets or sets the name of this type variable.|
|[Parent](/docs/api/csharp/typechecker.typevariable.parent.md)|Gets the parent of this type.|
|[TypeMembers](/docs/api/csharp/typechecker.typevariable.typemembers.md)|Gets the collection of members belonging to this type.|

