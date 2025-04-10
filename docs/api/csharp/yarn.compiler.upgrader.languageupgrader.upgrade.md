# Upgrade(UpgradeJob)

Method in [LanguageUpgrader](yarn.compiler.upgrader.languageupgrader.md)

## Summary

Upgrades a Yarn script from one version of the language to another, producing both the fully upgraded text as well as a collection of replacements.

```csharp
public static UpgradeResult Upgrade(UpgradeJob upgradeJob)
```

## Parameters

| Name                                                                                 | Description                 |
| ------------------------------------------------------------------------------------ | --------------------------- |
| [Yarn.Compiler.Upgrader.UpgradeJob](yarn.compiler.upgrader.upgradejob.md) upgradeJob | The upgrade job to perform. |

## Returns

An [UpgradeResult](yarn.compiler.upgrader.upgraderesult.md) object containing the results of the upgrade operation.
