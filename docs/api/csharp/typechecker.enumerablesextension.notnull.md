# EnumerablesExtension.NotNull(IEnumerable<T?>)

Method in [EnumerablesExtension](/docs/api/csharp/typechecker.enumerablesextension.md)

## Summary


Returns an enumerator containing all items of  `sequence`  that are not null.


```csharp
public static IEnumerable<T> NotNull<T>(this IEnumerable<T?> sequence) where T : class
```

## Parameters

|Name|Description|
|:---|:---|
|`IEnumerable<T?>` sequence|The sequence.|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of item in  `sequence` .|

## Returns

A sequence containing non-null elements of  `sequence` .

