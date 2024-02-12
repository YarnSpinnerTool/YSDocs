# AddLocalizedStrings(IEnumerable\<StringTableEntry>)

Method in [Localization](./)

## Summary

Adds a collection of strings to the runtime string table.

```csharp
public void AddLocalizedStrings(IEnumerable<StringTableEntry> stringTableEntries)
```

## Remarks

This method updates the localisation's runtime string table, which is useful for adding or changing the localisation during gameplay or in a built player. It doesn't modify the asset on disk, and any changes made will be lost when gameplay ends.

## Parameters

| Name                                                                                     | Description                                                                           |
| ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| strings                                                                                  | The collection of [StringTableEntry](../yarn.unity.stringtableentry/) objects to add. |
| `System.Collections.Generic.IEnumerable<Yarn.Unity.StringTableEntry>` stringTableEntries |                                                                                       |
