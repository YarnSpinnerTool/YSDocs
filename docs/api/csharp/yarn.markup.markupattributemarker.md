# MarkupAttributeMarker

Struct in [Yarn.Markup](yarn.markup.md)

Inherits from `System.ValueType`

## Summary

Represents a marker (e.g. `[a]` ) in line of marked up text.

```csharp
public struct MarkupAttributeMarker
```

## Remarks

You do not create instances of this struct yourself. It is created by objects that can parse markup, such as [Dialogue](yarn.dialogue.md) .

## Methods

| Name                                                                                      | Description                                                      |
| ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| [Equals(object)](yarn.markup.markupattributemarker.equals.md)                             |                                                                  |
| [GetHashCode()](yarn.markup.markupattributemarker.gethashcode.md)                         |                                                                  |
| [TryGetProperty(string,MarkupValue)](yarn.markup.markupattributemarker.trygetproperty.md) | Gets the property associated with the specified key, if present. |

## Properties

| Name                                                          | Description                                              |
| ------------------------------------------------------------- | -------------------------------------------------------- |
| [Name](yarn.markup.markupattributemarker.name.md)             | Gets the name of the marker.                             |
| [Position](yarn.markup.markupattributemarker.position.md)     | Gets the position of the marker in the plain text.       |
| [Properties](yarn.markup.markupattributemarker.properties.md) | Gets the list of properties associated with this marker. |
| [Type](yarn.markup.markupattributemarker.type.md)             | Gets the type of marker that this is.                    |

## TYPENAME\_UNKNOWN\_PLURAL

| Name                                                                                                                                                                                          | Description |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| [M:Yarn.Markup.MarkupAttributeMarker.op\_Equality(Yarn.Markup.MarkupAttributeMarker,Yarn.Markup.MarkupAttributeMarker)\~System.Boolean](yarn.markup.markupattributemarker.op_equality.md)     |             |
| [M:Yarn.Markup.MarkupAttributeMarker.op\_Inequality(Yarn.Markup.MarkupAttributeMarker,Yarn.Markup.MarkupAttributeMarker)\~System.Boolean](yarn.markup.markupattributemarker.op_inequality.md) |             |

## See Also

* Dialogue.ParseMarkup(string,string)
