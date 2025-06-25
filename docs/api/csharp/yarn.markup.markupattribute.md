# MarkupAttribute

Struct in [Yarn.Markup](yarn.markup.md)

Inherits from `System.ValueType`

## Summary

Represents a range of text in a marked-up string.

```csharp
public struct MarkupAttribute
```

## Remarks

You do not create instances of this struct yourself. It is created by\
objects that can parse markup, such as [LineParser](yarn.markup.lineparser.md) .

## Methods

| Name                                                                                  | Description                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Shift(int)](yarn.markup.markupattribute.shift.md)                                    | Creates a new [MarkupAttribute](yarn.markup.markupattribute.md) based on the current instance whose [Position](yarn.markup.markupattribute.position.md) is shifted towards the end of the string by `shift` characters. |
| [ToString()](yarn.markup.markupattribute.tostring.md)                                 |                                                                                                                                                                                                                         |
| [TryGetProperty(string,bool)](yarn.markup.markupattribute.trygetproperty-5.md)        | Gets a boolean property named `name` from this attribute, if present.                                                                                                                                                   |
| [TryGetProperty(string,int)](yarn.markup.markupattribute.trygetproperty-3.md)         | Gets an integer property named `name` from this attribute, if present.                                                                                                                                                  |
| [TryGetProperty(string,float)](yarn.markup.markupattribute.trygetproperty-2.md)       | Gets a float property named `name` from this attribute, if present.                                                                                                                                                     |
| [TryGetProperty(string,string?)](yarn.markup.markupattribute.trygetproperty-4.md)     | Gets a string property named `name` from this attribute, if present.                                                                                                                                                    |
| [TryGetProperty(string,MarkupValue)](yarn.markup.markupattribute.trygetproperty-1.md) | Gets a property named `name` from this attribute, if present.                                                                                                                                                           |

## Properties

| Name                                                    | Description                                                                    |
| ------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Length](yarn.markup.markupattribute.length.md)         | Gets the number of text elements in the plain text that this attribute covers. |
| [Name](yarn.markup.markupattribute.name.md)             | Gets the name of the attribute.                                                |
| [Position](yarn.markup.markupattribute.position.md)     | Gets the position in the plain text where this attribute begins.               |
| [Properties](yarn.markup.markupattribute.properties.md) | Gets the properties associated with this attribute.                            |

## See Also

* Yarn.Markup.LineParser.ParseString(System.String,System.String,System.Boolean,System.Boolean,System.Boolean):
