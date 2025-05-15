# TypeVariable.Parent

Property in [TypeVariable](/docs/api/csharp/typechecker.typevariable.md)

## Summary


Gets the parent of this type.


```csharp
public IType? Parent { get };
```

## Remarks

All types have  [Any](yarn.types.any.md)  as their
ultimate parent type (except for  [Any](yarn.types.any.md) 
itself.)

