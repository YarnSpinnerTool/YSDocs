# TypeMappings

Property in [BuiltinTypes](/api/csharp/yarn.builtintypes.md)

## Summary


Gets a dictionary that maps CLR types to their corresponding
Yarn types.


```csharp
public static IReadOnlyDictionary<System.Type, Yarn.IType> TypeMappings { get; } = new Dictionary<System.Type, Yarn.IType>
        {
            { typeof(string), BuiltinTypes.String },
            { typeof(bool), BuiltinTypes.Boolean },
            { typeof(int), BuiltinTypes.Number },
            { typeof(float), BuiltinTypes.Number },
            { typeof(double), BuiltinTypes.Number },
            { typeof(sbyte), BuiltinTypes.Number },
            { typeof(byte), BuiltinTypes.Number },
            { typeof(short), BuiltinTypes.Number },
            { typeof(ushort), BuiltinTypes.Number },
            { typeof(uint), BuiltinTypes.Number },
            { typeof(long), BuiltinTypes.Number },
            { typeof(ulong), BuiltinTypes.Number },
            { typeof(decimal), BuiltinTypes.Number },
            { typeof(object), BuiltinTypes.Any },
        };
```

