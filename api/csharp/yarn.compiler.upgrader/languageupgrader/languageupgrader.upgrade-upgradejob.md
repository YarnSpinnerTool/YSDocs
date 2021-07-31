# Upgrade\(UpgradeJob\)

Upgrades a Yarn script from one version of the language to another, producing both the fully upgraded text as well as a collection of replacements.

```csharp
public static UpgradeResult Upgrade(UpgradeJob upgradeJob)
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`UpgradeJob`](../upgradejob/) upgradeJob | The upgrade job to perform. |

## Return Type

[`UpgradeResult`](../upgraderesult/): An [`UpgradeResult`](../upgraderesult/) object containing the results of the upgrade operation.

## Namespace

[`Yarn.Compiler.Upgrader`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Upgrader/LanguageUpgrader.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Upgrader/LanguageUpgrader.cs#L213), line 213.

