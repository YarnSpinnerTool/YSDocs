# EnumTypeBuilder.FromEnum<TEnum>(string?)

Method in [EnumTypeBuilder](/docs/api/csharp/yarn.compiler.enumtypebuilder.md)

## Summary


Creates a new  <a href="yarn.enumtype.md">EnumType</a>  given a CLR enum type.


```csharp
public static EnumType FromEnum<TEnum>(string? description = null)
    where TEnum : System.Enum
```

## Parameters

|Name|Description|
|:---|:---|
|`string` description|An optional description to apply to the new Yarn enum type.|

## Type Parameters

|Name|Description|
|:---|:---|
|TEnum|The type of the CLR enum.|

## Returns

A Yarn type representing the enum.

