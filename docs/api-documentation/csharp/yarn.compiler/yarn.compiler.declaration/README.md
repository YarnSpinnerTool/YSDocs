# Declaration

Class in [Yarn.Compiler](../)

Inherits from `System.Object`

## Summary

Represents a variable declaration

```csharp
public class Declaration
```

## Fields

| Name                                                                    | Description                                                                                                                                   |
| ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| [ExternalDeclaration](yarn.compiler.declaration.externaldeclaration.md) | The string used for [SourceFileName](yarn.compiler.declaration.sourcefilename.md) if the Declaration was found outside of a Yarn source file. |

## Methods

| Name                                                                                                 | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| [CreateVariable(string,Yarn.IType,IConvertible,string)](yarn.compiler.declaration.createvariable.md) | Creates a new instance of the [Declaration](./) class, using the given name, type and default value. |
| [Equals(object)](yarn.compiler.declaration.equals.md)                                                |                                                                                                      |
| [GetHashCode()](yarn.compiler.declaration.gethashcode.md)                                            |                                                                                                      |
| [ToString()](yarn.compiler.declaration.tostring.md)                                                  |                                                                                                      |

## Properties

| Name                                                          | Description                                                                                                                                                                                                       |
| ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DefaultValue](yarn.compiler.declaration.defaultvalue.md)     | Gets the default value of this [Declaration](./) , if no value has been specified in code or is available from a [Dialogue](../../yarn/yarn.dialogue/) 's [IVariableStorage](../../yarn/yarn.ivariablestorage/) . |
| [Description](yarn.compiler.declaration.description.md)       | Gets a string describing the purpose of this [Declaration](./) .                                                                                                                                                  |
| [IsImplicit](yarn.compiler.declaration.isimplicit.md)         | Gets a value indicating whether get or sets a value indicating whether this Declaration was implicitly inferred from usage.                                                                                       |
| [IsVariable](yarn.compiler.declaration.isvariable.md)         | Gets a value indicating whether this Declaration represents a variable.                                                                                                                                           |
| [Name](yarn.compiler.declaration.name.md)                     | Gets the name of this Declaration.                                                                                                                                                                                |
| [Range](yarn.compiler.declaration.range.md)                   | Gets the range of text at which this declaration occurs.                                                                                                                                                          |
| [SourceFileLine](yarn.compiler.declaration.sourcefileline.md) | Gets the line number at which this Declaration was found in the source file.                                                                                                                                      |
| [SourceFileName](yarn.compiler.declaration.sourcefilename.md) | Gets the name of the file in which this Declaration was found.                                                                                                                                                    |
| [SourceNodeName](yarn.compiler.declaration.sourcenodename.md) | Gets the name of the node in which this Declaration was found.                                                                                                                                                    |
| [Type](yarn.compiler.declaration.type.md)                     | Gets the type of the variable, as represented by an object that implements [IType](../../yarn/yarn.itype/) .                                                                                                      |
