# DeclarationBuilder

Class in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Provides methods for constructing  <a href="yarn.compiler.declaration.md">Declaration</a>  objects.


```csharp
public class DeclarationBuilder
```

## Remarks


To use this class, create an instance of it, and call the
<code>With</code> -prefixed methods to set properties. When you're done, access
the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a>  property to get the final, constructed
<a href="yarn.compiler.declaration.md">Declaration</a> .


## Methods

|Name|Description|
|:---|:---|
|[WithDefaultValue(System.IConvertible)](/api/csharp/yarn.compiler.declarationbuilder.withdefaultvalue.md)|Sets the  <a href="yarn.compiler.declaration.defaultvalue.md">DefaultValue</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a> .|
|[WithDescription(string)](/api/csharp/yarn.compiler.declarationbuilder.withdescription.md)|Sets the  <a href="yarn.compiler.declaration.description.md">Description</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a> .|
|[WithImplicit(bool)](/api/csharp/yarn.compiler.declarationbuilder.withimplicit.md)|Sets the  <a href="yarn.compiler.declaration.isimplicit.md">IsImplicit</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a> .|
|[WithName(string)](/api/csharp/yarn.compiler.declarationbuilder.withname.md)|Sets the  <a href="yarn.compiler.declaration.name.md">Name</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a> .|
|[WithRange(Yarn.Compiler.Range)](/api/csharp/yarn.compiler.declarationbuilder.withrange.md)|Sets the  <a href="yarn.compiler.declaration.range.md">Range</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a> .|
|[WithSourceFileName(string)](/api/csharp/yarn.compiler.declarationbuilder.withsourcefilename.md)|Sets the  <a href="yarn.compiler.declaration.sourcefilename.md">SourceFileName</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a> .|
|[WithSourceNodeName(string)](/api/csharp/yarn.compiler.declarationbuilder.withsourcenodename.md)|Sets the  <a href="yarn.compiler.declaration.sourcenodename.md">SourceNodeName</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a> .|
|[WithType(IType)](/api/csharp/yarn.compiler.declarationbuilder.withtype.md)|Sets the  <a href="yarn.compiler.declaration.type.md">Type</a>  of the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a> .|

## Properties

|Name|Description|
|:---|:---|
|[Declaration](/api/csharp/yarn.compiler.declarationbuilder.declaration.md)|Gets the  <a href="yarn.compiler.declarationbuilder.declaration.md">Declaration</a>  instance constructed by this  <a href="yarn.compiler.declarationbuilder.md">DeclarationBuilder</a> .|

