# Declaration

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Represents a variable declaration


```csharp
public class Declaration
```

## Fields

|Name|Description|
|:---|:---|
|[ExternalDeclaration](/docs/api/csharp/yarn.compiler.declaration.externaldeclaration.md)|The string used for  <a href="yarn.compiler.declaration.sourcefilename.md">SourceFileName</a>  if the Declaration was found outside of a Yarn source file.|

## Methods

|Name|Description|
|:---|:---|
|[CreateVariable(string,IType,IConvertible,string?)](/docs/api/csharp/yarn.compiler.declaration.createvariable.md)|Creates a new instance of the  <a href="yarn.compiler.declaration.md">Declaration</a>  class, using the given name, type and default value.|
|[ToString()](/docs/api/csharp/yarn.compiler.declaration.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[DefaultValue](/docs/api/csharp/yarn.compiler.declaration.defaultvalue.md)|Gets the default value of this  <a href="yarn.compiler.declaration.md">Declaration</a> , if no value has been specified in code or is available from a  <a href="yarn.dialogue.md">Dialogue</a> 's  <a href="yarn.ivariablestorage.md">IVariableStorage</a> .|
|[Dependencies](/docs/api/csharp/yarn.compiler.declaration.dependencies.md)|Gets the collection of  <a href="yarn.compiler.declaration.md">Declaration</a>  objects that this <a href="yarn.compiler.declaration.md">Declaration</a>  depends upon the value of.|
|[Dependents](/docs/api/csharp/yarn.compiler.declaration.dependents.md)|Gets the collection of  <a href="yarn.compiler.declaration.md">Declaration</a>  objects whose value depends upon this  <a href="yarn.compiler.declaration.md">Declaration</a> .|
|[Description](/docs/api/csharp/yarn.compiler.declaration.description.md)|Gets a string describing the purpose of this  <a href="yarn.compiler.declaration.md">Declaration</a> .|
|[InitialValueParserContext](/docs/api/csharp/yarn.compiler.declaration.initialvalueparsercontext.md)|Gets or sets the parser context for the initial value provided in this variable's 'declare' statement, if any. This is only valid for variable declarations, not functions (because functions don't have a value.)|
|[IsImplicit](/docs/api/csharp/yarn.compiler.declaration.isimplicit.md)|Gets a value indicating whether this Declaration was implicitly inferred from usage.|
|[IsInlineExpansion](/docs/api/csharp/yarn.compiler.declaration.isinlineexpansion.md)|Gets a value indicating that this Declaration does not refer to a stored variable, and instead represents an inline-expanded expression (a 'smart variable').|
|[IsVariable](/docs/api/csharp/yarn.compiler.declaration.isvariable.md)|Gets a value indicating whether this Declaration represents a variable, and not a function.|
|[Name](/docs/api/csharp/yarn.compiler.declaration.name.md)|Gets the name of this Declaration.|
|[Range](/docs/api/csharp/yarn.compiler.declaration.range.md)|Gets the range of text at which this declaration occurs.|
|[SourceFileLine](/docs/api/csharp/yarn.compiler.declaration.sourcefileline.md)|Gets the line number at which this Declaration was found in the source file.|
|[SourceFileName](/docs/api/csharp/yarn.compiler.declaration.sourcefilename.md)|Gets the name of the file in which this Declaration was found.|
|[SourceNodeName](/docs/api/csharp/yarn.compiler.declaration.sourcenodename.md)|Gets the name of the node in which this Declaration was found.|
|[Type](/docs/api/csharp/yarn.compiler.declaration.type.md)|Gets the type of the variable, as represented by an object that implements  <a href="yarn.itype.md">IType</a> .|

