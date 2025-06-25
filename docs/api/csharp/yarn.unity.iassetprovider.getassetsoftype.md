# GetAssetsOfType\<T>()

Method in [IAssetProvider](yarn.unity.iassetprovider.md)

## Summary

Gets a collection of assets of type `T` from\
the target.

```csharp
public IEnumerable<T> GetAssetsOfType<T>()
    where T : UnityEngine.Object;
```

## Type Parameters

| Name | Description            |
| ---- | ---------------------- |
| T    | The type of the asset. |

## Returns

A collection of assets. This collection may be\
empty.
