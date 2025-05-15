# TypeVariable.TypeMembers

Property in [TypeVariable](/docs/api/csharp/typechecker.typevariable.md)

## Summary


Gets the collection of members belonging to this type.


```csharp
public IReadOnlyDictionary<string, ITypeMember> TypeMembers { get };
```

## Remarks


This collection is always empty, because a type variable represents
an unknown type.


