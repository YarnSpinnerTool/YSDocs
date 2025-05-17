# GeneratedVariableStorageExtensions.GetValueOrDefault(IGeneratedVariableStorage,string)

Method in [GeneratedVariableStorageExtensions](/docs/api/csharp/yarn.unity.generatedvariablestorageextensions.md)

## Summary


Gets a value for the variable  `variableName`  from
`storage` , or else returns the default value of
`T` .


```csharp
public static T? GetValueOrDefault<T>(this IGeneratedVariableStorage storage, string variableName)
    where T : IConvertible
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.IGeneratedVariableStorage](/docs/api/csharp/yarn.unity.igeneratedvariablestorage.md) storage|The generated variable storage class to get the value from.|
|`string` variableName|The name of the variable to get a value for.|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of the parameter to get a value for.|

## Returns

The value of  `variableName` , or the
default value of
`T` .

