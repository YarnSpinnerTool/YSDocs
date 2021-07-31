# Declaration

```csharp
[Serializable]
public class Declaration
```

## Methods

| Name | Description |
| :--- | :--- |
| [`CreateVariable(String, Object, String)`](declaration.createvariable-system.string-system.object-system.string.md) | Creates a new instance of the [`Declaration`](./) class, using the given `name` and default value. The [`ReturnType`](declaration.returntype.md) of the new instance will be configured based on the type of `defaultValue`, and the [`DeclarationType`](declaration.declarationtype.md) will be [`Variable`](../declaration.type/declaration.type.variable.md). All other properties will be their default values. |
| [`Equals(Object)`](declaration.equals-system.object.md) |  |
| [`GetHashCode()`](declaration.gethashcode.md) |  |
| [`ToString()`](declaration.tostring.md) |  |

## Properties

| Name | Description |
| :--- | :--- |
| [`DeclarationType`](declaration.declarationtype.md) | Gets the type of this declaration. |
| [`DefaultValue`](declaration.defaultvalue.md) | Gets the default value of this [`Declaration`](./), if no value has been specified in code or is available from a [`Dialogue`](../../yarn/dialogue/)'s [`IVariableStorage`](../../yarn/ivariablestorage/). |
| [`Description`](declaration.description.md) | Gets a string describing the purpose of this [`Declaration`](./). |
| [`Name`](declaration.name.md) | Gets the name of this Declaration. |
| [`Parameters`](declaration.parameters.md) | Gets the [`Declaration.Parameter`](../declaration.parameter/)s associated with this [`Declaration`](./). |
| [`ReturnType`](declaration.returntype.md) | Gets the return type of this declaration. |
| [`SourceFileLine`](declaration.sourcefileline.md) | The line number at which this Declaration was found in the source file. |
| [`SourceFileName`](declaration.sourcefilename.md) | Gets the name of the file in which this Declaration was found. |
| [`SourceNodeLine`](declaration.sourcenodeline.md) | Gets the line number at which this Declaration was found in the node indicated by [`SourceNodeName`](declaration.sourcenodename.md). |
| [`SourceNodeName`](declaration.sourcenodename.md) | Gets the name of the node in which this Declaration was found. |

## Fields

| Name | Description |
| :--- | :--- |
| [`ExternalDeclaration`](declaration.externaldeclaration.md) | The string used for [`SourceFileName`](declaration.sourcefilename.md) if the Declaration was found outside of a Yarn source file. |

## Namespace

[`Yarn.Compiler`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L167), line 167.

