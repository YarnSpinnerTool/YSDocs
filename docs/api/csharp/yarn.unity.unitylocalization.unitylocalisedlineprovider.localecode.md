# UnityLocalisedLineProvider.LocaleCode

Property in [UnityLocalisedLineProvider](/docs/api/csharp/yarn.unity.unitylocalization.unitylocalisedlineprovider.md)

## Summary


Gets the user's current locale identifier, as a BCP-47 code.


```csharp
public override string LocaleCode
{
            get; set; }
```

## Remarks


This value is used to control how certain replacement markers behave
(for example, the  <code>[plural]</code>  marker, which behaves differently
depending on the user's locale.)


