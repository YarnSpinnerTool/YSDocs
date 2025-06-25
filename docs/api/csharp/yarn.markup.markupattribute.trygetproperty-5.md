# TryGetProperty(string,bool)

Method in [MarkupAttribute](yarn.markup.markupattribute.md)

## Summary

Gets a boolean property named `name` from this\
attribute, if present.

```csharp
public readonly bool TryGetProperty(string name, out bool result)
```

## Parameters

| Name          | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| `string` name | The name of the property.                                    |
| `bool` result | On return, the property's value if found, or `false` if not. |

## Returns

`true` if a property named `name` was found; `false`\
otherwise.
