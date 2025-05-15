# DeclarationBuilder

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Provides methods for constructing  [Declaration](yarn.compiler.declaration.md)  objects.


```csharp
public class DeclarationBuilder
```

## Remarks


To use this class, create an instance of it, and call the
`With` -prefixed methods to set properties. When you're done, access
the  [Declaration](yarn.compiler.declarationbuilder.declaration.md)  property to get the final, constructed
[Declaration](yarn.compiler.declaration.md) .


## Methods

|Name|Description|
|:---|:---|
|[WithDefaultValue(System.IConvertible)](/docs/api/csharp/yarn.compiler.declarationbuilder.withdefaultvalue.md)|Sets the  [Declaration](yarn.compiler.declaration.defaultvalue.md">DefaultValue</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md) .|
|[WithDescription(string?)](/docs/api/csharp/yarn.compiler.declarationbuilder.withdescription.md)|Sets the  [Declaration](yarn.compiler.declaration.description.md">Description</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md) .|
|[WithImplicit(bool)](/docs/api/csharp/yarn.compiler.declarationbuilder.withimplicit.md)|Sets the  [Declaration](yarn.compiler.declaration.isimplicit.md">IsImplicit</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md) .|
|[WithName(string)](/docs/api/csharp/yarn.compiler.declarationbuilder.withname.md)|Sets the  [Declaration](yarn.compiler.declaration.name.md">Name</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md) .|
|[WithRange(Yarn.Compiler.Range)](/docs/api/csharp/yarn.compiler.declarationbuilder.withrange.md)|Sets the  [Declaration](yarn.compiler.declaration.range.md">Range</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md) .|
|[WithSourceFileName(string)](/docs/api/csharp/yarn.compiler.declarationbuilder.withsourcefilename.md)|Sets the  [Declaration](yarn.compiler.declaration.sourcefilename.md">SourceFileName</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md) .|
|[WithSourceNodeName(string)](/docs/api/csharp/yarn.compiler.declarationbuilder.withsourcenodename.md)|Sets the  [Declaration](yarn.compiler.declaration.sourcenodename.md">SourceNodeName</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md) .|
|[WithType(IType)](/docs/api/csharp/yarn.compiler.declarationbuilder.withtype.md)|Sets the  [Declaration](yarn.compiler.declaration.type.md">Type</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md) .|

## Properties

|Name|Description|
|:---|:---|
|[Declaration](/docs/api/csharp/yarn.compiler.declarationbuilder.declaration.md)|Gets the  [DeclarationBuilder](yarn.compiler.declarationbuilder.declaration.md">Declaration</a>  instance constructed by this  <a href="yarn.compiler.declarationbuilder.md) .|

