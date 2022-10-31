# YarnParameterAttribute.Injector

Property in [YarnParameterAttribute](api/csharp/yarn.unity.yarnparameterattribute.md)

## Summary


The custom injector for this parameter.


```csharp
public string Injector { get; set; }
```

## Remarks


Similar to  <a href="yarn.unity.yarncommandattribute.injector.md">Injector</a> .

If this is not defined on a parameter, or if the injector is not
static or doesn't exist, or returns a type that is not assignable
to the parameter's type, then it will be use the default method,
which is to search for the game object name, and search for the
target component type on that object.


