# AssemblyExtensions.GetLoadableTypes(Assembly)

Method in [AssemblyExtensions](/api/csharp/yarn.unity.assemblyextensions.md)

## Summary


Assembly.GetTypes() can throw in some cases.  This extension
will catch that exception and return only the types which were
successfully loaded from the assembly.


```csharp
public static IEnumerable<System.Type> GetLoadableTypes(this Assembly @this)
```

## Parameters

|Name|Description|
|:---|:---|
|`Assembly` @this||

