# MemoryVariableStore

Class in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


A simple concrete implementation of  <a href="yarn.ivariablestorage.md">IVariableStorage</a> 
that keeps all variables in memory.


```csharp
public class MemoryVariableStore : IVariableStorage
```

## Methods

|Name|Description|
|:---|:---|
|[Clear()](/docs/api/csharp/yarn.memoryvariablestore.clear.md)|Removes all variables from storage.|
|[GetVariableKind(string)](/docs/api/csharp/yarn.memoryvariablestore.getvariablekind.md)|Gets the kind of variable named  <code>name</code> .|
|[SetValue(string,bool)](/docs/api/csharp/yarn.memoryvariablestore.setvalue-3.md)|Stores a  <code>bool</code>  in this VariableStorage.|
|[SetValue(string,float)](/docs/api/csharp/yarn.memoryvariablestore.setvalue-2.md)|Stores a  <code>float</code>  in this VariableStorage.|
|[SetValue(string,string)](/docs/api/csharp/yarn.memoryvariablestore.setvalue-1.md)|Stores a  <code>string</code>  in this VariableStorage.|
|[TryGetValue<T>(string,T?)](/docs/api/csharp/yarn.memoryvariablestore.trygetvalue.md)|Given a variable name, attempts to fetch a value for the variable, either from storage, initial values found in  <a href="yarn.ivariableaccess.program.md">Program</a> , or by evaluating a smart variable found in  <a href="yarn.ivariableaccess.program.md">Program</a> .|

## Properties

|Name|Description|
|:---|:---|
|[Program](/docs/api/csharp/yarn.memoryvariablestore.program.md)|Gets or sets the Yarn  <a href="yarn.ivariableaccess.program.md">Program</a>  that stores information about the initial values of variables, and is able to produce values for smart variables.|
|[SmartVariableEvaluator](/docs/api/csharp/yarn.memoryvariablestore.smartvariableevaluator.md)|Gets or sets the object to use when evaluating smart variables.|

