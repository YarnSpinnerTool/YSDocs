# YarnImporter

A  for Yarn assets. The actual asset used and referenced at runtime and in the editor will be a , which this class wraps around creating the asset's corresponding meta file.

```csharp
public class YarnImporter : ScriptedImporter
```

## Methods

| Name | Description |
| :--- | :--- |
| [`AddLocalization(String, TextAsset)`](yarnimporter.addlocalization-system.string-textasset.md) |  |
| [`OnImportAsset(AssetImportContext)`](yarnimporter.onimportasset-assetimportcontext.md) |  |
| [`SupportsRemappedAssetType(System.Type)`](yarnimporter.supportsremappedassettype-system.type.md) |  |

## Properties

| Name | Description |
| :--- | :--- |
| [`AllLocalizations`](yarnimporter.alllocalizations.md) |  |
| [`DefaultLocalizationName`](yarnimporter.defaultlocalizationname.md) | Returns the locale name to use as the base localization ID for a newly created Yarn script. This will be either the first entry in `ProjectSettings.TextProjectLanguages`, or if this is not set, the user's current culture. |
| [`DestinationProgram`](yarnimporter.destinationprogram.md) |  |
| [`ExternalLocalizations`](yarnimporter.externallocalizations.md) |  |
| [`StringsAvailable`](yarnimporter.stringsavailable.md) |  |

## Fields

| Name | Description |
| :--- | :--- |
| [`AnyImplicitStringIDs`](yarnimporter.anyimplicitstringids.md) |  |
| [`baseLanguage`](yarnimporter.baselanguage.md) |  |
| [`baseLanguageID`](yarnimporter.baselanguageid.md) |  |
| [`isSuccesfullyParsed`](yarnimporter.issuccesfullyparsed.md) |  |
| [`localizationDatabase`](yarnimporter.localizationdatabase.md) |  |
| [`parseErrorMessage`](yarnimporter.parseerrormessage.md) |  |
| [`stringIDs`](yarnimporter.stringids.md) |  |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Editor/YarnImporter.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Editor/YarnImporter.cs#L65), line 65.

