# StringTableEntry.Lock

Field in [StringTableEntry](api/csharp/yarn.unity.stringtableentry.md)

## Summary


A string used as part of a mechanism for checking if translated
versions of this string are out of date.


```csharp
public string Lock;
```

## Remarks

<p>
This field contains the first 8 characters of the SHA-256 hash of
the line's text as it appeared in the base localization CSV file.
</p> <p>
When a new StringTableEntry is created in a localized CSV file for a
.yarn file, the Lock value is copied over from the base CSV file,
and used for the translated entry. 
</p> <p>
Because the base localization CSV is regenerated every time the
.yarn file is imported, the base localization Lock value will change
if a line's text changes. This means that if the base lock and
translated lock differ, the translated line is out of date, and
needs to be updated.
</p>

