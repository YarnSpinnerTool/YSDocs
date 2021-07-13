# Declaration Class


```csharp
[Serializable]
public class Declaration
```



## Methods
|Name|Description|
|:---|:---|
|[CreateVariable(String, Object, String)](/api/csharp/yarn.compiler/declaration.createvariable-system.string,system.object,system.string-.md)| Creates a new instance of the [`Declaration`](/api/csharp/yarn.compiler/declaration.md) class, using the given <code data-dev-comment-type="paramref" class="paramref">name</code> and default value. The [`ReturnType`](/api/csharp/yarn.compiler/declaration.returntype.md) of the new instance will be configured based on the type of <code data-dev-comment-type="paramref" class="paramref">defaultValue</code>, and the [`DeclarationType`](/api/csharp/yarn.compiler/declaration.declarationtype.md) will be [`Variable`](/api/csharp/yarn.compiler/declaration.type.variable.md). All other properties will be their default values. |
|[Equals(Object)](/api/csharp/yarn.compiler/declaration.equals-system.object-.md)||
|[GetHashCode()](/api/csharp/yarn.compiler/declaration.gethashcode.md)||
|[ToString()](/api/csharp/yarn.compiler/declaration.tostring.md)||
## Properties
|Name|Description|
|:---|:---|
|[DeclarationType](/api/csharp/yarn.compiler/declaration.declarationtype.md)| Gets the type of this declaration. |
|[DefaultValue](/api/csharp/yarn.compiler/declaration.defaultvalue.md)| Gets the default value of this [`Declaration`](/api/csharp/yarn.compiler/declaration.md), if no value has been specified in code or is available from a [`Dialogue`](/api/csharp/yarn/dialogue.md)'s [`IVariableStorage`](/api/csharp/yarn/ivariablestorage.md). |
|[Description](/api/csharp/yarn.compiler/declaration.description.md)| Gets a string describing the purpose of this [`Declaration`](/api/csharp/yarn.compiler/declaration.md). |
|[Name](/api/csharp/yarn.compiler/declaration.name.md)| Gets the name of this Declaration. |
|[Parameters](/api/csharp/yarn.compiler/declaration.parameters.md)| Gets the [`Declaration.Parameter`](/api/csharp/yarn.compiler/declaration.parameter.md)s associated with this [`Declaration`](/api/csharp/yarn.compiler/declaration.md). |
|[ReturnType](/api/csharp/yarn.compiler/declaration.returntype.md)| Gets the return type of this declaration. |
|[SourceFileLine](/api/csharp/yarn.compiler/declaration.sourcefileline.md)| The line number at which this Declaration was found in the source file. |
|[SourceFileName](/api/csharp/yarn.compiler/declaration.sourcefilename.md)| Gets the name of the file in which this Declaration was found. |
|[SourceNodeLine](/api/csharp/yarn.compiler/declaration.sourcenodeline.md)| Gets the line number at which this Declaration was found in the node indicated by [`SourceNodeName`](/api/csharp/yarn.compiler/declaration.sourcenodename.md). |
|[SourceNodeName](/api/csharp/yarn.compiler/declaration.sourcenodename.md)| Gets the name of the node in which this Declaration was found. |
## Fields
|Name|Description|
|:---|:---|
|[ExternalDeclaration](/api/csharp/yarn.compiler/declaration.externaldeclaration.md)| The string used for [`SourceFileName`](/api/csharp/yarn.compiler/declaration.sourcefilename.md) if the Declaration was found outside of a Yarn source file. |
<div class="class-metadata">

Namespace: [`Yarn.Compiler`](/api/csharp/yarn.compiler/README.md), Assembly: YarnSpinner.Compiler.dll
</div>

## Source
Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L167), line 167.
