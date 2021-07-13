# LineProviderBehaviour Class

A <see cref="!:MonoBehaviour"></see> that produces [`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md)s.


```csharp
public abstract class LineProviderBehaviour : MonoBehaviour
```
## Remarks

[`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md)s use a [`LineProviderBehaviour`](/api/csharp/yarn.unity/lineproviderbehaviour.md) to get [`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md)s,
which contain the localized information that [`DialogueViewBase`](/api/csharp/yarn.unity/dialogueviewbase.md) classes use to present content to the
player. 

Subclasses of this abstract class may return subclasses of
LocalizedLine. For example, [`AudioLineProvider`](/api/csharp/yarn.unity/audiolineprovider.md) returns
an [`AudioLocalizedLine`](/api/csharp/yarn.unity/audiolocalizedline.md), which includes <see cref="!:AudioClip"></see>; views that make use of audio can then access
this additional data.




## Properties
|Name|Description|
|:---|:---|
|[`CurrentTextLanguageCode`](/api/csharp/yarn.unity/lineproviderbehaviour.currenttextlanguagecode.md)||
|[`LinesAvailable`](/api/csharp/yarn.unity/lineproviderbehaviour.linesavailable.md)||
## Methods
|Name|Description|
|:---|:---|
|[`GetLocalizedLine(Line)`](/api/csharp/yarn.unity/lineproviderbehaviour.getlocalizedline-yarn.line-.md)||
|[`PrepareForLines(IEnumerable<String>)`](/api/csharp/yarn.unity/lineproviderbehaviour.prepareforlines-ienumerable-system.string--.md)||
|[`Start()`](/api/csharp/yarn.unity/lineproviderbehaviour.start.md)||
## Fields
|Name|Description|
|:---|:---|
|[`localizationDatabase`](/api/csharp/yarn.unity/lineproviderbehaviour.localizationdatabase.md)| The data source for this line provider. |
|[`textLanguageCodeOverride`](/api/csharp/yarn.unity/lineproviderbehaviour.textlanguagecodeoverride.md)|Specifies the language code to use for text content for this [`LineProviderBehaviour`](/api/csharp/yarn.unity/lineproviderbehaviour.md), overriding project settings.|
<div class="class-metadata">

Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/LineProviders/LineProviderBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/LineProviders/LineProviderBase.cs#L23), line 23.
