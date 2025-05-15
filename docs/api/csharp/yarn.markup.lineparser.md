# LineParser

Class in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

Inherits from `System.Object`

## Summary


Parses text and produces markup information.


```csharp
public sealed class LineParser : IDisposable
```

## Fields

|Name|Description|
|:---|:---|
|[CharacterAttribute](/docs/api/csharp/yarn.markup.lineparser.characterattribute.md)|The name of the implicitly-generated  `character`  attribute.|
|[CharacterAttributeNameProperty](/docs/api/csharp/yarn.markup.lineparser.characterattributenameproperty.md)|The name of the 'name' property, on the implicitly-generated `character`  attribute.|
|[NoMarkupAttribute](/docs/api/csharp/yarn.markup.lineparser.nomarkupattribute.md)|The name of the attribute to use to indicate that no marker processing should occur.|
|[ReplacementMarkerContents](/docs/api/csharp/yarn.markup.lineparser.replacementmarkercontents.md)|The name of the property in replacement attributes that contains the text of the attribute.|
|[TrimWhitespaceProperty](/docs/api/csharp/yarn.markup.lineparser.trimwhitespaceproperty.md)|The name of the property to use to signify that trailing whitespace should be trimmed if a tag had preceding whitespace or begins the line. This property must be a bool value.|

## Methods

|Name|Description|
|:---|:---|
|[DeregisterMarkerProcessor(string)](/docs/api/csharp/yarn.markup.lineparser.deregistermarkerprocessor.md)|Removes any marker processor associated with a given marker name.|
|[Dispose()](/docs/api/csharp/yarn.markup.lineparser.dispose.md)||
|[ExpandSubstitutions(string,IList<string>)](/docs/api/csharp/yarn.markup.lineparser.expandsubstitutions.md)|Replaces all substitution markers in a text with the given substitution list.|
|[ParseString(string,string,bool)](/docs/api/csharp/yarn.markup.lineparser.parsestring.md)|Parses a string of text and produces a markup parse result.|
|[RegisterMarkerProcessor(string,IAttributeMarkerProcessor)](/docs/api/csharp/yarn.markup.lineparser.registermarkerprocessor.md)|Registers an object as a marker processor for a given marker name.|

## Structs

|Name|Description|
|:---|:---|
|[MarkupDiagnostic](/docs/api/csharp/yarn.markup.lineparser.markupdiagnostic.md)|Represents a diagnostic message produced during markup parsing.|

