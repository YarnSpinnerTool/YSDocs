# UsesAddressableAssets

Property in [Localization](yarn.unity.localization.md)

## Summary

Gets a value indicating whether this [Localization](yarn.unity.localization.md)\
makes use of Addressable Assets ( `true` ), or if it\
stores its assets as direct references ( `false` ).

```csharp
public bool UsesAddressableAssets { get; internal set; }
```

## Remarks

If this property is `true` , `Yarn.Unity.Localization.GetLocalizedObjectAsync1(System.String)</code> and <code>Yarn.Unity.Localization.ContainsLocalizedObject1(System.String)` should not be used to retrieve\
localised objects. Instead, the Addressable Assets API should be\
used.
