# OutputFile

Struct in [UpgradeResult](/docs/api/csharp/yarn.compiler.upgrader.upgraderesult.md)

Inherits from `System.ValueType`

## Summary


A file generated as part of an upgrade.


```csharp
public struct OutputFile
```

## Fields

|Name|Description|
|:---|:---|
|[Diagnostics](/docs/api/csharp/yarn.compiler.upgrader.upgraderesult.outputfile.diagnostics.md)|The diagnostics produced for this file as a result of the upgrade process.|
|[IsNewFile](/docs/api/csharp/yarn.compiler.upgrader.upgraderesult.outputfile.isnewfile.md)|Indicates whether this  [OutputFile](yarn.compiler.upgrader.upgraderesult.outputfile.md)  represents a new file to be created. If this is  `true` ,  [OriginalSource](yarn.compiler.upgrader.upgraderesult.outputfile.originalsource.md)  will be the empty string, and  [Replacements](yarn.compiler.upgrader.upgraderesult.outputfile.replacements.md)  will be empty.|
|[OriginalSource](/docs/api/csharp/yarn.compiler.upgrader.upgraderesult.outputfile.originalsource.md)|The original text of the file, prior to upgrades.|
|[Path](/docs/api/csharp/yarn.compiler.upgrader.upgraderesult.outputfile.path.md)|The path of the file.|
|[Replacements](/docs/api/csharp/yarn.compiler.upgrader.upgraderesult.outputfile.replacements.md)|The list of replacements needed to be made in order to go from [UpgradedSource](yarn.compiler.upgrader.upgraderesult.outputfile.originalsource.md">OriginalSource</a>  to  <a href="yarn.compiler.upgrader.upgraderesult.outputfile.upgradedsource.md) .|

## Properties

|Name|Description|
|:---|:---|
|[UpgradedSource](/docs/api/csharp/yarn.compiler.upgrader.upgraderesult.outputfile.upgradedsource.md)|The upgraded text of the file.|

