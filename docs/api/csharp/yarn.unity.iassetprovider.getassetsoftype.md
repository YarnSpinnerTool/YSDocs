# IAssetProvider.GetAssetsOfType<T>()

Method in [IAssetProvider](/docs/api/csharp/yarn.unity.iassetprovider.md)

## Summary


Gets a collection of assets of type  <code>T</code>  from
the target.


```csharp
public IEnumerable<T> GetAssetsOfType<T>()
    where T : UnityEngine.Object;
```

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of the asset.|

## Returns

A collection of assets. This collection may be
empty.

