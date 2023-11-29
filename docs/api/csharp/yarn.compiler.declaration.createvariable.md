# Declaration.CreateVariable(string,Yarn.IType,IConvertible,string)

Method in [Declaration](/docs/api/csharp/yarn.compiler.declaration.md)

## Summary


Creates a new instance of the  <a href="yarn.compiler.declaration.md">Declaration</a>  class,
using the given name, type and default value.


```csharp
public static Declaration CreateVariable(string name, Yarn.IType type, IConvertible defaultValue, string description = null)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the new declaration.|
|[Yarn.IType](/docs/api/csharp/yarn.itype.md) type|The type of the declaration.|
|`System.IConvertible` defaultValue|The default value of the declaration. This must be a string, a number (integer or floating-point), or boolean value.|
|`string` description|The description of the new declaration.|

## Returns

A new instance of the  <a href="yarn.compiler.declaration.md">Declaration</a> 
class.

