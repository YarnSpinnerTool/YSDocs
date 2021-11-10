# UpgradeResult.OutputFile

```csharp
public struct OutputFile
```

## Fields

| Name                                                           | Description                                                                                                                                                                                                                                                                                                                                                    |
| -------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`Annotations`](upgraderesult.outputfile.annotations.md)       |                                                                                                                                                                                                                                                                                                                                                                |
| [`IsNewFile`](upgraderesult.outputfile.isnewfile.md)           | Indicates whether this [`UpgradeResult.OutputFile`](./) represents a new file to be created. If this is `` `, [ ``OriginalSource`](/api/csharp/yarn.compiler.upgrader/upgraderesult.outputfile.originalsource.md) will be the empty string, and [`Replacements\`]\(/api/csharp/yarn.compiler.upgrader/upgraderesult.outputfile.replacements.md) will be empty. |
| [`OriginalSource`](upgraderesult.outputfile.originalsource.md) |                                                                                                                                                                                                                                                                                                                                                                |
| [`Path`](upgraderesult.outputfile.path.md)                     |                                                                                                                                                                                                                                                                                                                                                                |
| [`Replacements`](upgraderesult.outputfile.replacements.md)     |                                                                                                                                                                                                                                                                                                                                                                |
| [`UpgradedSource`](upgraderesult.outputfile.upgradedsource.md) |                                                                                                                                                                                                                                                                                                                                                                |

## Namespace

[`Yarn.Compiler.Upgrader`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Upgrader/LanguageUpgrader.cs](https://github.com/YarnSpinnerTool/YarnSpinner/blob/develop/YarnSpinner.Compiler/Upgrader/LanguageUpgrader.cs#L50), line 50.
