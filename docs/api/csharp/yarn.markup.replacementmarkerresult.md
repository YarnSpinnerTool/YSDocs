# ReplacementMarkerResult

Struct in [Yarn.Markup](/docs/api/csharp/yarn.markup.md)

Inherits from `System.ValueType`

## Summary


A bundle of results from processing replacement markers.


```csharp
public struct ReplacementMarkerResult
```

## Constructors

|Name|Description|
|:---|:---|
|[ReplacementMarkerResult(List<LineParser.MarkupDiagnostic>,int)](/docs/api/csharp/yarn.markup.replacementmarkerresult..ctor-1.md)|Convenience constructor for replacement markup results.|
|[ReplacementMarkerResult(int)](/docs/api/csharp/yarn.markup.replacementmarkerresult..ctor-2.md)|Convenience form of  <a href="yarn.markup.replacementmarkerresult..ctor-1.md">ReplacementMarkerResult(List&lt;LineParser.MarkupDiagnostic&gt;,int)</a>  for when there are no diagnostics.|

## Fields

|Name|Description|
|:---|:---|
|[Diagnostics](/docs/api/csharp/yarn.markup.replacementmarkerresult.diagnostics.md)|The collection of diagnostics produced during processing, if any.|
|[InvisibleCharacters](/docs/api/csharp/yarn.markup.replacementmarkerresult.invisiblecharacters.md)|The number of invisible characters added into the line during processing.|

## See Also

* [IAttributeMarkerProcessor](/docs/api/csharp/yarn.markup.iattributemarkerprocessor.md): Provides a mechanism for producing replacement text for a marker.

