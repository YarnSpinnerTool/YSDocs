# Substitution

Class in [TypeChecker](/docs/api/csharp/typechecker.md)

Inherits from `System.Collections.Generic.Dictionary`2`

## Summary


A substitution is a mapping between type variables and types (or other
type variables). It is produced during the process of type resolution by
the  <code>TypeChecker.Solver</code>  class.


```csharp
public class Substitution : Dictionary<TypeVariable, IType>
```

## Methods

|Name|Description|
|:---|:---|
|[Clone()](/docs/api/csharp/typechecker.substitution.clone.md)|Returns a duplicate of this  <a href="typechecker.substitution.md">Substitution</a> .|

