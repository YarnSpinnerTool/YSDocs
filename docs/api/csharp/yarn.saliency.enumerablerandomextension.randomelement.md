# EnumerableRandomExtension.RandomElement<T>(IEnumerable<T>)

Method in [EnumerableRandomExtension](/docs/api/csharp/yarn.saliency.enumerablerandomextension.md)

## Summary


Returns a random element from  <code>enumerable</code> .


```csharp
public static T RandomElement<T>(this IEnumerable<T> enumerable)
```

## Remarks


This method uses System.Random to make a selection, which is
cryptographically insecure. This means that this method should not
be used for security-critical decisions.


## Parameters

|Name|Description|
|:---|:---|
|`System.Collections.Generic.IEnumerable<T>` enumerable|The collection to choose an item from.|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of element in  <code>enumerable</code> .|

## Returns

A random element in  <code>enumerable</code> .

