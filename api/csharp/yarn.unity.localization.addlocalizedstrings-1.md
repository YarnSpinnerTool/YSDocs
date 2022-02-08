# Localization.AddLocalizedStrings(IEnumerable<KeyValuePair<string, string>>)

Method in [Localization](/api/csharp/yarn.unity.localization.md)

## Summary


Adds a collection of strings to the runtime string table.


```csharp
public void AddLocalizedStrings(IEnumerable<KeyValuePair<string, string>> strings)
```

## Remarks


This method updates the localisation's runtime string table, which
is useful for adding or changing the localisation during gameplay or
in a built player. It doesn't modify the asset on disk, and any
changes made will be lost when gameplay ends.


## Parameters

|Name|Description|
|:---|:---|
|`IEnumerable<KeyValuePair<string, string>>` strings|The collection of keys and strings to add.|

