# YarnProject

Class in [Yarn.Unity](../)

Inherits from `UnityEngine.ScriptableObject`

## Summary

```csharp
public class YarnProject : ScriptableObject
```

## Fields

| Name                                                                               | Description                                                                                                                                                                 |
| ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [baseLocalization](yarn.unity.yarnproject.baselocalization.md)                     |                                                                                                                                                                             |
| [compiledYarnProgram](yarn.unity.yarnproject.compiledyarnprogram.md)               |                                                                                                                                                                             |
| [lineMetadata](yarn.unity.yarnproject.linemetadata.md)                             |                                                                                                                                                                             |
| [localizations](yarn.unity.yarnproject.localizations.md)                           |                                                                                                                                                                             |
| [localizationType](yarn.unity.yarnproject.localizationtype.md)                     |                                                                                                                                                                             |
| [searchAssembliesForActions](yarn.unity.yarnproject.searchassembliesforactions.md) | The names of assemblies that `ActionManager` should look for commands and functions in when this project is loaded into a [DialogueRunner](../yarn.unity.dialoguerunner/) . |

## Methods

| Name                                                                            | Description                                                          |
| ------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| [GetHeaders(string)](yarn.unity.yarnproject.getheaders.md)                      | Gets the headers for the requested node.                             |
| [GetLineIDsForNodes(IEnumerable)](yarn.unity.yarnproject.getlineidsfornodes.md) | Returns a list of all line and option IDs within the requested nodes |
| [GetLocalization(string)](yarn.unity.yarnproject.getlocalization.md)            |                                                                      |

## Properties

| Name                                                     | Description                                                                                                                                                          |
| -------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [InitialValues](yarn.unity.yarnproject.initialvalues.md) | The default values of all declared or inferred variables in the [Program](yarn.unity.yarnproject.program.md) . Organised by their name as written in the yarn files. |
| [NodeNames](yarn.unity.yarnproject.nodenames.md)         | The names of all nodes contained within the [Program](yarn.unity.yarnproject.program.md) .                                                                           |
| [Program](yarn.unity.yarnproject.program.md)             | Gets the Yarn Program stored in this project.                                                                                                                        |
