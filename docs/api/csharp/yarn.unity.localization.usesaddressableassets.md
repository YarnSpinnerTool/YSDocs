# Localization.UsesAddressableAssets

Property in [Localization](/docs/api/csharp/yarn.unity.localization.md)

## Summary


Gets a value indicating whether this  <a href="yarn.unity.localization.md">Localization</a> 
makes use of Addressable Assets ( `true` ), or if it
stores its assets as direct references ( `false` ).


```csharp
public bool UsesAddressableAssets { get; internal set; }
```

## Remarks


If this property is  `true` ,  `Yarn.Unity.Localization.GetLocalizedObjectAsync``1(System.String)`  and  `Yarn.Unity.Localization.ContainsLocalizedObject``1(System.String)`  should not be used to retrieve
localised objects. Instead, the Addressable Assets API should be
used.


