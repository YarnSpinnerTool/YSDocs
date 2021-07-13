# UpgradeResult.OutputFile.IsNewFile Field

Indicates whether this [`UpgradeResult.OutputFile`](/api/csharp/yarn.compiler.upgrader/upgraderesult.outputfile.md) represents
a new file to be created. If this is ``, [`OriginalSource`](/api/csharp/yarn.compiler.upgrader/upgraderesult.outputfile.originalsource.md) will be the
empty string, and [`Replacements`](/api/csharp/yarn.compiler.upgrader/upgraderesult.outputfile.replacements.md) will be empty.


```csharp
public bool IsNewFile
```



<div class="class-metadata">

Parent: [`UpgradeResult.OutputFile`](/api/csharp/yarn.compiler.upgrader/upgraderesult.outputfile.md), Namespace: [`Yarn.Compiler.Upgrader`](/api/csharp/yarn.compiler.upgrader/README.md), Assembly: YarnSpinner.Compiler.dll
</div>

## Source
Defined in [YarnSpinner.Compiler/Upgrader/LanguageUpgrader.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Upgrader/LanguageUpgrader.cs#L64), line 64.
