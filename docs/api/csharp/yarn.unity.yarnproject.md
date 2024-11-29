# YarnProject

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.ScriptableObject`

## Summary



```csharp
public class YarnProject : ScriptableObject
```

## Classes

|Name|Description|
|:---|:---|
|[ShadowTableDictionary](/docs/api/csharp/yarn.unity.yarnproject.shadowtabledictionary.md)||

## Fields

|Name|Description|
|:---|:---|
|[baseLocalization](/docs/api/csharp/yarn.unity.yarnproject.baselocalization.md)||
|[compiledYarnProgram](/docs/api/csharp/yarn.unity.yarnproject.compiledyarnprogram.md)||
|[lineMetadata](/docs/api/csharp/yarn.unity.yarnproject.linemetadata.md)||
|[localizations](/docs/api/csharp/yarn.unity.yarnproject.localizations.md)||
|[localizationType](/docs/api/csharp/yarn.unity.yarnproject.localizationtype.md)||

## Methods

|Name|Description|
|:---|:---|
|[GetHeaders(string)](/docs/api/csharp/yarn.unity.yarnproject.getheaders.md)|Gets the headers for the requested node.|
|[GetLineIDsForNodes(IEnumerable<string>)](/docs/api/csharp/yarn.unity.yarnproject.getlineidsfornodes.md)|Returns a list of all line and option IDs within the requested nodes|
|[GetLocalization(string)](/docs/api/csharp/yarn.unity.yarnproject.getlocalization.md)|Gets a Localization given a locale code.|

## Properties

|Name|Description|
|:---|:---|
|[InitialValues](/docs/api/csharp/yarn.unity.yarnproject.initialvalues.md)|The default values of all declared or inferred variables in the  <a href="yarn.unity.yarnproject.program.md">Program</a> . Organised by their name as written in the yarn files.|
|[NodeNames](/docs/api/csharp/yarn.unity.yarnproject.nodenames.md)|The names of all nodes contained within the  <a href="yarn.unity.yarnproject.program.md">Program</a> .|
|[Program](/docs/api/csharp/yarn.unity.yarnproject.program.md)|Gets the Yarn Program stored in this project.|

## Structs

|Name|Description|
|:---|:---|
|[ShadowTableEntry](/docs/api/csharp/yarn.unity.yarnproject.shadowtableentry.md)||

