# Program.TryGetInitialValue(string,T)

Method in [Program](/docs/api/csharp/yarn.program.md)

## Summary


Attempts to fetch a value for a variable named  <code>variableName</code>  from this program's collection of initial
values.


```csharp
public bool TryGetInitialValue<T>(string variableName, out T result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` variableName|The name of the variable to retrieve a value for.|
|`T` result|On return, contains the value of the variable, or the default value of  <code>T</code>  if not known. Depending on what  <code>T</code>  is, this value may be <code>null</code> .|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of variable to retrieve.|

## Returns

<code>true</code>  if an initial value for  <code>variableName</code>  was found;  <code>false</code> 
otherwise.

