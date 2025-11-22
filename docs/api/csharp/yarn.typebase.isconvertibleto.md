# IsConvertibleTo(TypeBase)

Method in [TypeBase](yarn.typebase.md)

## Summary

Checks if this type is convertible to the type represented by`otherType` .

```csharp
public bool IsConvertibleTo(TypeBase otherType)
```

## Remarks

A type is convertible to another type if:

1. there is an explicit conversion available, or
2. it is a descendant of that type, or
3. the two types are identical.

## Parameters

| Name                                        | Description        |
| ------------------------------------------- | ------------------ |
| [Yarn.TypeBase](yarn.typebase.md) otherType | The type to check. |

## Returns

`true` if this type is convertible to`otherType` .
