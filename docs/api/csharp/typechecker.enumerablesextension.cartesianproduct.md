# EnumerablesExtension.CartesianProduct(IEnumerable<IEnumerable<T>>)

Method in [EnumerablesExtension](/docs/api/csharp/typechecker.enumerablesextension.md)

## Summary


Gets the Cartesian product of 2 or more sequences.


```csharp
public static IEnumerable<IEnumerable<T>> CartesianProduct<T>
        (this IEnumerable<IEnumerable<T>> sequences)
```

## Parameters

|Name|Description|
|:---|:---|
|`IEnumerable<IEnumerable<T>>` sequences|The sequences to combine.|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of the values in the sequences.|

## Returns

The Cartesian product of the sequences.

