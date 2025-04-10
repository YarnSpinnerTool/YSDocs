# GetChecksum(string)

Method in [CRC32](yarn.utility.crc32.md)

## Summary

Computes a CRC32 checksum from the given string.

```csharp
public static uint GetChecksum(string s)
```

## Remarks

This method converts the string to a UTF-8 encoding, and then computes a CRC32 checksum from those bytes.

## Parameters

| Name       | Description                            |
| ---------- | -------------------------------------- |
| `string` s | The string to generate a checksum for. |

## Returns

A CRC32 checksum derived from `s` .
