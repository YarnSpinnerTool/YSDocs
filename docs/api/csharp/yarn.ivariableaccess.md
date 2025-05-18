# IVariableAccess

Interface in [Yarn](/docs/api/csharp/yarn.md)

## Summary

Provides a mechanism for retrieving values.

```csharp
public interface IVariableAccess
```

## Methods

|Name|Description|
|:---|:---|
|[GetVariableKind(string)](/docs/api/csharp/yarn.ivariableaccess.getvariablekind.md)|Gets the kind of variable named  <code>name</code> .|
|[TryGetValue<T>(string,T?)](/docs/api/csharp/yarn.ivariableaccess.trygetvalue.md)|Given a variable name, attempts to fetch a value for the variable, either from storage, initial values found in  <a href="yarn.ivariableaccess.program.md">Program</a> , or by evaluating a smart variable found in  <a href="yarn.ivariableaccess.program.md">Program</a> .|

## Properties

|Name|Description|
|:---|:---|
|[Program](/docs/api/csharp/yarn.ivariableaccess.program.md)|Gets or sets the Yarn  <a href="yarn.ivariableaccess.program.md">Program</a>  that stores information about the initial values of variables, and is able to produce values for smart variables.|
|[SmartVariableEvaluator](/docs/api/csharp/yarn.ivariableaccess.smartvariableevaluator.md)|Gets or sets the object to use when evaluating smart variables.|

