# Upgrade(UpgradeJob)

Method in [LanguageUpgrader](./)

## Summary

Upgrades a Yarn script from one version of the language to another, producing both the fully upgraded text as well as a collection of replacements.

```csharp
public static UpgradeResult Upgrade(UpgradeJob upgradeJob)
```

## Parameters

| Name                                                                                  | Description                 |
| ------------------------------------------------------------------------------------- | --------------------------- |
| [Yarn.Compiler.Upgrader.UpgradeJob](../yarn.compiler.upgrader.upgradejob/) upgradeJob | The upgrade job to perform. |

## Returns

An [UpgradeResult](../yarn.compiler.upgrader.upgraderesult/) object containing the results of the upgrade operation.
