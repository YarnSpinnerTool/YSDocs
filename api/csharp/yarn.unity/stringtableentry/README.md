# StringTableEntry

```csharp
public struct StringTableEntry
```

## Constructors

| Name | Description |
| :--- | :--- |
| [`StringTableEntry(StringTableEntry)`](stringtableentry._ctor-stringtableentry.md) |  |

## Fields

| Name | Description |
| :--- | :--- |
| [`Comment`](stringtableentry.comment.md) | A comment used to describe this line to translators. |
| [`File`](stringtableentry.file.md) | The name of the Yarn script in which this line was originally found. |
| [`ID`](stringtableentry.id.md) | The line ID for this line. This value will be the same across all localizations. |
| [`Language`](stringtableentry.language.md) | The language that the line is written in. |
| [`LineNumber`](stringtableentry.linenumber.md) | The line number in the file indicated by [`File`](stringtableentry.file.md) at which the original version of this line can be found. |
| [`Lock`](stringtableentry.lock.md) | A string used as part of a mechanism for checking if translated versions of this string are out of date. |
| [`Node`](stringtableentry.node.md) | The name of the node in which this line was originally found. |
| [`Text`](stringtableentry.text.md) | The text of this line, in the language specified by [`Language`](stringtableentry.language.md). |

## Methods

| Name | Description |
| :--- | :--- |
| [`CreateCSV(IEnumerable<StringTableEntry>)`](stringtableentry.createcsv-ienumerable-stringtableentry.md) |  |
| [`Equals(Object)`](stringtableentry.equals-system.object.md) |  |
| [`GetHashCode()`](stringtableentry.gethashcode.md) |  |
| [`ParseFromCSV(String)`](stringtableentry.parsefromcsv-system.string.md) | Reads comma-separated value ata from `sourceText`, and produces a collection of [`StringTableEntry`](./) structs. |
| [`ToString()`](stringtableentry.tostring.md) |  |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/StringTableEntry.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/StringTableEntry.cs#L7), line 7.

