# YarnProject

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.ScriptableObject`

## Summary



```csharp
public class YarnProject : ScriptableObject
```

## Fields

|Name|Description|
|:---|:---|
|[baseLocalization](/api/csharp/yarn.unity.yarnproject.baselocalization.md)||
|[compiledYarnProgram](/api/csharp/yarn.unity.yarnproject.compiledyarnprogram.md)||
|[lineMetadata](/api/csharp/yarn.unity.yarnproject.linemetadata.md)||
|[localizations](/api/csharp/yarn.unity.yarnproject.localizations.md)||
|[localizationType](/api/csharp/yarn.unity.yarnproject.localizationtype.md)||
|[searchAssembliesForActions](/api/csharp/yarn.unity.yarnproject.searchassembliesforactions.md)|The names of assemblies that  <code>ActionManager</code>  should look for commands and functions in when this project is loaded into a <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .|

## Methods

|Name|Description|
|:---|:---|
|[GetHeaders(string)](/api/csharp/yarn.unity.yarnproject.getheaders.md)|Gets the headers for the requested node.|
|[GetLineIDsForNodes(IEnumerable<string>)](/api/csharp/yarn.unity.yarnproject.getlineidsfornodes.md)|Returns a list of all line and option IDs within the requested nodes|
|[GetLocalization(string)](/api/csharp/yarn.unity.yarnproject.getlocalization.md)||

## Properties

|Name|Description|
|:---|:---|
|[InitialValues](/api/csharp/yarn.unity.yarnproject.initialvalues.md)|The default values of all declared or inferred variables in the <a href="yarn.unity.yarnproject.program.md">Program</a> . Organised by their name as written in the yarn files.|
|[NodeNames](/api/csharp/yarn.unity.yarnproject.nodenames.md)|The names of all nodes contained within the  <a href="yarn.unity.yarnproject.program.md">Program</a> .|
|[Program](/api/csharp/yarn.unity.yarnproject.program.md)|Gets the Yarn Program stored in this project.|

