# StringTableEntry

Struct in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `System.ValueType`

## Summary



```csharp
public struct StringTableEntry
```

## Fields

|Name|Description|
|:---|:---|
|[Comment](/api/csharp/yarn.unity.stringtableentry.comment.md)|A comment used to describe this line to translators.|
|[File](/api/csharp/yarn.unity.stringtableentry.file.md)|The name of the Yarn script in which this line was originally found.|
|[ID](/api/csharp/yarn.unity.stringtableentry.id.md)|The line ID for this line. This value will be the same across all localizations.|
|[Language](/api/csharp/yarn.unity.stringtableentry.language.md)|The language that the line is written in.|
|[LineNumber](/api/csharp/yarn.unity.stringtableentry.linenumber.md)|The line number in the file indicated by  <a href="yarn.unity.stringtableentry.file.md">File</a>  at which the original version of this line can be found.|
|[Lock](/api/csharp/yarn.unity.stringtableentry.lock.md)|A string used as part of a mechanism for checking if translated versions of this string are out of date.|
|[Node](/api/csharp/yarn.unity.stringtableentry.node.md)|The name of the node in which this line was originally found.|
|[Text](/api/csharp/yarn.unity.stringtableentry.text.md)|The text of this line, in the language specified by  <a href="yarn.unity.stringtableentry.language.md">Language</a> .|

## Methods

|Name|Description|
|:---|:---|
|[StringTableEntry(StringTableEntry)](/api/csharp/yarn.unity.stringtableentry..ctor.md)||
|[CreateCSV(IEnumerable<StringTableEntry>)](/api/csharp/yarn.unity.stringtableentry.createcsv.md)||
|[Equals(object)](/api/csharp/yarn.unity.stringtableentry.equals.md)||
|[GetHashCode()](/api/csharp/yarn.unity.stringtableentry.gethashcode.md)||
|[ParseFromCSV(string)](/api/csharp/yarn.unity.stringtableentry.parsefromcsv.md)|Reads comma-separated value ata from  <code>sourceText</code> , and produces a collection of  <a href="yarn.unity.stringtableentry.md">StringTableEntry</a>  structs.|
|[ToString()](/api/csharp/yarn.unity.stringtableentry.tostring.md)||

