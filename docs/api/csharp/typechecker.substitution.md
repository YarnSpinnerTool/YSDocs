# Substitution

Class in [TypeChecker](typechecker.md)

Inherits from `System.Collections.Generic.Dictionary`2\`

## Summary

A substitution is a mapping between type variables and types (or other type variables). It is produced during the process of type resolution by the `TypeChecker.Solver` class.

```csharp
public class Substitution : Dictionary<TypeVariable, IType>
```

## Methods

| Name                                         | Description                                                               |
| -------------------------------------------- | ------------------------------------------------------------------------- |
| [Clone()](typechecker.substitution.clone.md) | Returns a duplicate of this [Substitution](typechecker.substitution.md) . |
