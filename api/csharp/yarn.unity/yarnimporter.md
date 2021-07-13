# YarnImporter Class

A <see cref="!:ScriptedImporter"></see> for Yarn assets. The actual asset used and referenced at runtime and in the editor will be a <see cref="!:YarnScript"></see>, which this class wraps around creating the asset's corresponding meta file.


```csharp
public class YarnImporter : ScriptedImporter
```



## Methods
|Name|Description|
|:---|:---|
|[`AddLocalization(String, TextAsset)`](/api/csharp/yarn.unity/yarnimporter.addlocalization-system.string,textasset-.md)||
|[`OnImportAsset(AssetImportContext)`](/api/csharp/yarn.unity/yarnimporter.onimportasset-assetimportcontext-.md)||
|[`SupportsRemappedAssetType(System.Type)`](/api/csharp/yarn.unity/yarnimporter.supportsremappedassettype-system.type-.md)||
## Properties
|Name|Description|
|:---|:---|
|[`AllLocalizations`](/api/csharp/yarn.unity/yarnimporter.alllocalizations.md)||
|[`DefaultLocalizationName`](/api/csharp/yarn.unity/yarnimporter.defaultlocalizationname.md)| Returns the locale name to use as the base localization ID for a newly created Yarn script. This will be either the first entry in `ProjectSettings.TextProjectLanguages`, or if this is not set, the user's current culture. |
|[`DestinationProgram`](/api/csharp/yarn.unity/yarnimporter.destinationprogram.md)||
|[`ExternalLocalizations`](/api/csharp/yarn.unity/yarnimporter.externallocalizations.md)||
|[`StringsAvailable`](/api/csharp/yarn.unity/yarnimporter.stringsavailable.md)||
## Fields
|Name|Description|
|:---|:---|
|[`AnyImplicitStringIDs`](/api/csharp/yarn.unity/yarnimporter.anyimplicitstringids.md)||
|[`baseLanguage`](/api/csharp/yarn.unity/yarnimporter.baselanguage.md)||
|[`baseLanguageID`](/api/csharp/yarn.unity/yarnimporter.baselanguageid.md)||
|[`isSuccesfullyParsed`](/api/csharp/yarn.unity/yarnimporter.issuccesfullyparsed.md)||
|[`localizationDatabase`](/api/csharp/yarn.unity/yarnimporter.localizationdatabase.md)||
|[`parseErrorMessage`](/api/csharp/yarn.unity/yarnimporter.parseerrormessage.md)||
|[`stringIDs`](/api/csharp/yarn.unity/yarnimporter.stringids.md)||
<div class="class-metadata">

Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Editor/YarnImporter.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Editor/YarnImporter.cs#L65), line 65.
