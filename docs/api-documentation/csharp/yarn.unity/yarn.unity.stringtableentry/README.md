# StringTableEntry

Struct in [Yarn.Unity](../)

Inherits from `System.ValueType`

## Summary

```csharp
public struct StringTableEntry
```

## Constructors

| Name                                                                       | Description                                                                                                |
| -------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| [StringTableEntry(StringTableEntry)](yarn.unity.stringtableentry..ctor.md) | Initializes a new instance of the [StringTableEntry](./) struct, copying values from an existing instance. |

## Fields

| Name                                                    | Description                                                                                                                                   |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| [Comment](yarn.unity.stringtableentry.comment.md)       | A comment used to describe this line to translators.                                                                                          |
| [File](yarn.unity.stringtableentry.file.md)             | The name of the Yarn script in which this line was originally found.                                                                          |
| [ID](yarn.unity.stringtableentry.id.md)                 | The line ID for this line. This value will be the same across all localizations.                                                              |
| [Language](yarn.unity.stringtableentry.language.md)     | The language that the line is written in.                                                                                                     |
| [LineNumber](yarn.unity.stringtableentry.linenumber.md) | The line number in the file indicated by [File](yarn.unity.stringtableentry.file.md) at which the original version of this line can be found. |
| [Lock](yarn.unity.stringtableentry.lock.md)             | A string used as part of a mechanism for checking if translated versions of this string are out of date.                                      |
| [Node](yarn.unity.stringtableentry.node.md)             | The name of the node in which this line was originally found.                                                                                 |
| [Text](yarn.unity.stringtableentry.text.md)             | The text of this line, in the language specified by [Language](yarn.unity.stringtableentry.language.md) .                                     |

## Methods

| Name                                                                | Description                                                                                                       |
| ------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| [CreateCSV(IEnumerable)](yarn.unity.stringtableentry.createcsv.md)  | Creates a CSV-formatted string containing data from `entries` .                                                   |
| [Equals(object)](yarn.unity.stringtableentry.equals.md)             |                                                                                                                   |
| [GetHashCode()](yarn.unity.stringtableentry.gethashcode.md)         |                                                                                                                   |
| [ParseFromCSV(string)](yarn.unity.stringtableentry.parsefromcsv.md) | Reads comma-separated value data from `sourceText` , and produces a collection of [StringTableEntry](./) structs. |
| [ToString()](yarn.unity.stringtableentry.tostring.md)               |                                                                                                                   |
