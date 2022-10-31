# Localization.UsesAddressableAssets

Property in [Localization](api/csharp/yarn.unity.localization.md)

## Summary


Gets a value indicating whether this  <a href="yarn.unity.localization.md">Localization</a> 
makes use of Addressable Assets ( <code>true</code> ), or if it
stores its assets as direct references ( <code>false</code> ).


```csharp
public bool UsesAddressableAssets { get; internal set; }
```

## Remarks


If this property is  <code>true</code> ,  <code>Yarn.Unity.Localization.GetLocalizedObject``1(System.String)</code>  and  <code>Yarn.Unity.Localization.ContainsLocalizedObject``1(System.String)</code>  should not be used to
retrieve localised objects. Instead, the Addressable Assets API
should be used.


