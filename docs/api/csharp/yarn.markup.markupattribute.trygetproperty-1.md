# TryGetProperty(string,MarkupValue)

Method in [MarkupAttribute](yarn.markup.markupattribute.md)

## Summary

Gets a property named `name` from this\
attribute, if present.

```csharp
public readonly bool TryGetProperty(string name, out MarkupValue result)
```

## Parameters

| Name                                                         | Description                                               |
| ------------------------------------------------------------ | --------------------------------------------------------- |
| `string` name                                                | The name of the property.                                 |
| [Yarn.Markup.MarkupValue](yarn.markup.markupvalue.md) result | On return, the property's value if found, or zero if not. |

## Returns

`true` if a property named `name` was found; `false`\
otherwise.
