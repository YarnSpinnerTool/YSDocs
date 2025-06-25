# Shift(int)

Method in [MarkupAttribute](yarn.markup.markupattribute.md)

## Summary

Creates a new [MarkupAttribute](yarn.markup.markupattribute.md) based on the current\
instance whose [Position](yarn.markup.markupattribute.position.md) is shifted towards the end of\
the string by `shift` characters.

```csharp
public readonly MarkupAttribute Shift(int shift)
```

## Parameters

| Name        | Description                           |
| ----------- | ------------------------------------- |
| `int` shift | The number of characters to shift by. |

## Returns

A new [MarkupAttribute](yarn.markup.markupattribute.md) with an updated [Position](yarn.markup.markupattribute.position.md) .
