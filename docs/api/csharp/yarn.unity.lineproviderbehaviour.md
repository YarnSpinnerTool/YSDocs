# LineProviderBehaviour

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary


A  <code>UnityEngine.MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.


```csharp
public abstract class LineProviderBehaviour : MonoBehaviour, ILineProvider
```

## Remarks

<a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> s use a  <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a> 
to get  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, which contain the localized
information that is presented to the player through dialogue views.


## Methods

|Name|Description|
|:---|:---|
|[DeregisterMarkerProcessor(string)](/docs/api/csharp/yarn.unity.lineproviderbehaviour.deregistermarkerprocessor.md)|Removes all marker processors that handle markers named  <code>attributeName</code> .|
|[GetLocalizedLineAsync(Line,CancellationToken)](/docs/api/csharp/yarn.unity.lineproviderbehaviour.getlocalizedlineasync.md)|Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the specified <a href="yarn.line.md">Line</a> .|
|[PrepareForLinesAsync(IEnumerable<string>,CancellationToken)](/docs/api/csharp/yarn.unity.lineproviderbehaviour.prepareforlinesasync.md)|Signals to the line provider that lines with the provided line IDs may be presented shortly.|
|[RegisterMarkerProcessor(string,IAttributeMarkerProcessor)](/docs/api/csharp/yarn.unity.lineproviderbehaviour.registermarkerprocessor.md)|Adds a new marker processor to the line provider.|
|[Start()](/docs/api/csharp/yarn.unity.lineproviderbehaviour.start.md)|Called by Unity when the  <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a>  has first appeared in the scene.|

## Properties

|Name|Description|
|:---|:---|
|[LinesAvailable](/docs/api/csharp/yarn.unity.lineproviderbehaviour.linesavailable.md)||
|[LocaleCode](/docs/api/csharp/yarn.unity.lineproviderbehaviour.localecode.md)|Gets the user's current locale identifier, as a BCP-47 code.|
|[YarnProject](/docs/api/csharp/yarn.unity.lineproviderbehaviour.yarnproject.md)|The  <a href="ilineprovider.yarnproject.md">YarnProject</a>  that contains the localized data for lines.|

## See Also

* [DialogueViewBase](/docs/api/csharp/yarn.unity.dialogueviewbase.md): Implements the Yarn Spinner 2 callback-based API for dialogue views using Yarn Spinner 3.

