# YarnActionAttribute.Name

Property in [YarnActionAttribute](/docs/api/csharp/yarn.unity.yarnactionattribute.md)

## Summary


The name of the command or function, as it exists in Yarn.


```csharp
public string? Name { get; set; }
```

## Remarks


This value does not have to be the same as the name of the method.
For example, you could have a method named "`WalkToPoint`", and
expose it to Yarn as a command named "`walk_to_point`".


