# Position

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Represents a position in a multi-line string.


```csharp
public class Position
```

## Constructors

|Name|Description|
|:---|:---|
|[Position()](/docs/api/csharp/yarn.compiler.position..ctor-2.md)|Initialises a new instance of the Position class.|
|[Position(int,int)](/docs/api/csharp/yarn.compiler.position..ctor-1.md)|Initialises a new instance of the Position class with the specified line and character.|

## Fields

|Name|Description|
|:---|:---|
|[InvalidPosition](/docs/api/csharp/yarn.compiler.position.invalidposition.md)|Represents the default value for a Position.|

## Methods

|Name|Description|
|:---|:---|
|[Equals(object)](/docs/api/csharp/yarn.compiler.position.equals.md)||
|[GetHashCode()](/docs/api/csharp/yarn.compiler.position.gethashcode.md)||
|[ToString()](/docs/api/csharp/yarn.compiler.position.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[Character](/docs/api/csharp/yarn.compiler.position.character.md)|Gets or sets the zero-indexed character number of this position.|
|[IsValid](/docs/api/csharp/yarn.compiler.position.isvalid.md)|Gets a value indicating whether this position has a zero or positive line and character number.|
|[Line](/docs/api/csharp/yarn.compiler.position.line.md)|Gets or sets the zero-indexed line of this position.|

## TYPENAME_UNKNOWN_PLURAL

|Name|Description|
|:---|:---|
|[M:Yarn.Compiler.Position.op_Addition(Yarn.Compiler.Position,Yarn.Compiler.Position)](/docs/api/csharp/yarn.compiler.position.op_addition.md)|Adds two positions by component and returns the result.|
|[M:Yarn.Compiler.Position.op_GreaterThanOrEqual(Yarn.Compiler.Position,Yarn.Compiler.Position)](/docs/api/csharp/yarn.compiler.position.op_greaterthanorequal.md)|Compares two positions and returns true if  <code>a</code>  is equal to or after  <code>b</code> .|
|[M:Yarn.Compiler.Position.op_LessThanOrEqual(Yarn.Compiler.Position,Yarn.Compiler.Position)](/docs/api/csharp/yarn.compiler.position.op_lessthanorequal.md)|Compares two positions and returns true if  <code>a</code>  is equal to or before  <code>b</code> .|

