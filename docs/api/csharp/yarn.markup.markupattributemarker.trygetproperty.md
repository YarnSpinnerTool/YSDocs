# TryGetProperty(string,MarkupValue)

Method in [MarkupAttributeMarker](yarn.markup.markupattributemarker.md)

## Summary

Gets the property associated with the specified key, if present.

```csharp
public bool TryGetProperty(string name, out MarkupValue result)
```

## Parameters

| Name                                                         | Description                                                                                                                                                                                                     |
| ------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `string` name                                                | The name of the property to get.                                                                                                                                                                                |
| [Yarn.Markup.MarkupValue](yarn.markup.markupvalue.md) result | When this method returns, contains the value associated with the specified key, if the key is found; otherwise, the default [MarkupValue](yarn.markup.markupvalue.md) . This parameter is passed uninitialized. |

## Returns

`true` if the [MarkupAttributeMarker](yarn.markup.markupattributemarker.md) contains an element with the specified key; otherwise, `false` .
