# Declaration.CreateVariable(string,Yarn.IType,IConvertible,string)

Method in [Declaration](/api/csharp/yarn.compiler.declaration.md)

## Summary


Creates a new instance of the  <a href="yarn.compiler.declaration.md">Declaration</a>  class,
using the given  <code>name</code>  and default value. The
<code>ReturnType</code>  of the new instance will be configured
based on the type of  <code>defaultValue</code> , and the
<code>DeclarationType</code>  will be  <code>Type.Variable</code> . All other properties will be their
default values.


```csharp
public static Declaration CreateVariable(string name, Yarn.IType type, IConvertible defaultValue, string description = null)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the new declaration.|
|`System.IConvertible` defaultValue|The default value of the declaration. This must be a string, a number (integer or floating-point), or boolean value.|
|`string` description|The description of the new declaration.|
|[Yarn.IType](/api/csharp/yarn.itype.md) type||

## Returns

A new instance of the  <a href="yarn.compiler.declaration.md">Declaration</a> 
class.

