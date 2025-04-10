# DeclarationBuilder

Class in [Yarn.Compiler](yarn.compiler.md)

Inherits from `System.Object`

## Summary

Provides methods for constructing [Declaration](yarn.compiler.declaration.md) objects.

```csharp
public class DeclarationBuilder
```

## Remarks

To use this class, create an instance of it, and call the `With` -prefixed methods to set properties. When you're done, access the [Declaration](yarn.compiler.declarationbuilder.declaration.md) property to get the final, constructed [Declaration](yarn.compiler.declaration.md) .

## Methods

| Name                                                                                          | Description                                                                                                                                    |
| --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| [WithDefaultValue(System.IConvertible)](yarn.compiler.declarationbuilder.withdefaultvalue.md) | Sets the [DefaultValue](yarn.compiler.declaration.defaultvalue.md) of the [Declaration](yarn.compiler.declarationbuilder.declaration.md) .     |
| [WithDescription(string)](yarn.compiler.declarationbuilder.withdescription.md)                | Sets the [Description](yarn.compiler.declaration.description.md) of the [Declaration](yarn.compiler.declarationbuilder.declaration.md) .       |
| [WithImplicit(bool)](yarn.compiler.declarationbuilder.withimplicit.md)                        | Sets the [IsImplicit](yarn.compiler.declaration.isimplicit.md) of the [Declaration](yarn.compiler.declarationbuilder.declaration.md) .         |
| [WithName(string)](yarn.compiler.declarationbuilder.withname.md)                              | Sets the [Name](yarn.compiler.declaration.name.md) of the [Declaration](yarn.compiler.declarationbuilder.declaration.md) .                     |
| [WithRange(Yarn.Compiler.Range)](yarn.compiler.declarationbuilder.withrange.md)               | Sets the [Range](yarn.compiler.declaration.range.md) of the [Declaration](yarn.compiler.declarationbuilder.declaration.md) .                   |
| [WithSourceFileName(string)](yarn.compiler.declarationbuilder.withsourcefilename.md)          | Sets the [SourceFileName](yarn.compiler.declaration.sourcefilename.md) of the [Declaration](yarn.compiler.declarationbuilder.declaration.md) . |
| [WithSourceNodeName(string)](yarn.compiler.declarationbuilder.withsourcenodename.md)          | Sets the [SourceNodeName](yarn.compiler.declaration.sourcenodename.md) of the [Declaration](yarn.compiler.declarationbuilder.declaration.md) . |
| [WithType(IType)](yarn.compiler.declarationbuilder.withtype.md)                               | Sets the [Type](yarn.compiler.declaration.type.md) of the [Declaration](yarn.compiler.declarationbuilder.declaration.md) .                     |

## Properties

| Name                                                           | Description                                                                                                                                                      |
| -------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Declaration](yarn.compiler.declarationbuilder.declaration.md) | Gets the [Declaration](yarn.compiler.declarationbuilder.declaration.md) instance constructed by this [DeclarationBuilder](yarn.compiler.declarationbuilder.md) . |
