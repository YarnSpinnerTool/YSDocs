# ILineProvider.LocaleCode

Property in [ILineProvider](/docs/api/csharp/ilineprovider.md)

## Summary


Gets the user's current locale identifier, as a BCP-47 code.


```csharp
public string LocaleCode { get; }
```

## Remarks


This value is used to control how certain replacement markers behave
(for example, the  <code>[plural]</code>  marker, which behaves differently
depending on the user's locale.)


