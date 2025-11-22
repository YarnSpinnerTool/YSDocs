# Program

Class in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


A compiled Yarn program.


```csharp
public class Program
```

## Methods

|Name|Description|
|:---|:---|
|[GetVariableKind(string)](/docs/api/csharp/yarn.program.getvariablekind.md)|Gets a value indicating the kind of variable  <code>name</code>  represents.|
|[LineIDsForNode(string)](/docs/api/csharp/yarn.program.lineidsfornode.md)|Identifies and returns a list of all line and option IDs inside the node.|
|[ToString()](/docs/api/csharp/yarn.program.tostring.md)||
|[TryGetInitialValue<T>(string,T)](/docs/api/csharp/yarn.program.trygetinitialvalue.md)|Attempts to fetch a value for a variable named  <code>variableName</code>  from this program's collection of initial values.|

## Properties

|Name|Description|
|:---|:---|
|[InitialValues](/docs/api/csharp/yarn.program.initialvalues.md)|The collection of initial values for variables; if a PUSH_VARIABLE instruction is run, and the value is not found in the storage, this value will be used|
|[Name](/docs/api/csharp/yarn.program.name.md)|The name of the program.|
|[Nodes](/docs/api/csharp/yarn.program.nodes.md)|The collection of nodes in this program.|

