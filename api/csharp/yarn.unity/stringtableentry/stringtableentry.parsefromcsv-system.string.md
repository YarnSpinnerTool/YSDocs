# ParseFromCSV\(String\)

Reads comma-separated value ata from `sourceText`, and produces a collection of [`StringTableEntry`](./) structs.

```csharp
public static IEnumerable<StringTableEntry> ParseFromCSV(string sourceText)
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) sourceText | A string containing CSV-formatted data. |

## Return Type

`IEnumerable<StringTableEntry>`: The parsed collection of [`StringTableEntry`](./) structs.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/StringTableEntry.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/StringTableEntry.cs#L110), line 110.

