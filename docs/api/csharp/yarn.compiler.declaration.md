# Declaration

Class in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Represents a variable declaration


```csharp
public class Declaration
```

## Fields

|Name|Description|
|:---|:---|
|[ExternalDeclaration](/api/csharp/yarn.compiler.declaration.externaldeclaration.md)|The string used for  <a href="yarn.compiler.declaration.sourcefilename.md">SourceFileName</a>  if the Declaration was found outside of a Yarn source file.|

## Methods

|Name|Description|
|:---|:---|
|[CreateVariable(string,Yarn.IType,IConvertible,string)](/api/csharp/yarn.compiler.declaration.createvariable.md)|Creates a new instance of the  <a href="yarn.compiler.declaration.md">Declaration</a>  class, using the given name, type and default value.|
|[Equals(object)](/api/csharp/yarn.compiler.declaration.equals.md)||
|[GetHashCode()](/api/csharp/yarn.compiler.declaration.gethashcode.md)||
|[ToString()](/api/csharp/yarn.compiler.declaration.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[DefaultValue](/api/csharp/yarn.compiler.declaration.defaultvalue.md)|Gets the default value of this  <a href="yarn.compiler.declaration.md">Declaration</a> , if no value has been specified in code or is available from a  <a href="yarn.dialogue.md">Dialogue</a> 's  <a href="yarn.ivariablestorage.md">IVariableStorage</a> .|
|[Description](/api/csharp/yarn.compiler.declaration.description.md)|Gets a string describing the purpose of this  <a href="yarn.compiler.declaration.md">Declaration</a> .|
|[IsImplicit](/api/csharp/yarn.compiler.declaration.isimplicit.md)|Gets a value indicating whether get or sets a value indicating whether this Declaration was implicitly inferred from usage.|
|[IsVariable](/api/csharp/yarn.compiler.declaration.isvariable.md)|Gets a value indicating whether this Declaration represents a variable.|
|[Name](/api/csharp/yarn.compiler.declaration.name.md)|Gets the name of this Declaration.|
|[Range](/api/csharp/yarn.compiler.declaration.range.md)|Gets the range of text at which this declaration occurs.|
|[SourceFileLine](/api/csharp/yarn.compiler.declaration.sourcefileline.md)|Gets the line number at which this Declaration was found in the source file.|
|[SourceFileName](/api/csharp/yarn.compiler.declaration.sourcefilename.md)|Gets the name of the file in which this Declaration was found.|
|[SourceNodeName](/api/csharp/yarn.compiler.declaration.sourcenodename.md)|Gets the name of the node in which this Declaration was found.|
|[Type](/api/csharp/yarn.compiler.declaration.type.md)|Gets the type of the variable, as represented by an object that implements  <a href="yarn.itype.md">IType</a> .|

