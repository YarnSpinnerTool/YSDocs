# TryGetProperty(string,float)

Method in [MarkupAttribute](yarn.markup.markupattribute.md)

## Summary

Gets a float property named `name` from this\
attribute, if present.

```csharp
public bool TryGetProperty(string name, out float result)
```

## Parameters

| Name           | Description                                               |
| -------------- | --------------------------------------------------------- |
| `string` name  | The name of the property.                                 |
| `float` result | On return, the property's value if found, or zero if not. |

## Returns

`true` if a property named `name` was found; `false`\
otherwise.
