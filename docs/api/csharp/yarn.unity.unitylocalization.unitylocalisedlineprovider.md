# UnityLocalisedLineProvider

Class in [Yarn.Unity.UnityLocalization](/docs/api/csharp/yarn.unity.unitylocalization.md)

Inherits from [`LineProviderBehaviour`](/docs/api/csharp/yarn.unity.lineproviderbehaviour.md)

## Summary


A line provider that uses the Unity Localization system to get localized
content for Yarn lines.


```csharp
public class UnityLocalisedLineProvider : LineProviderBehaviour
```

## Methods

|Name|Description|
|:---|:---|
|[DeregisterMarkerProcessor(string)](/docs/api/csharp/yarn.unity.unitylocalization.unitylocalisedlineprovider.deregistermarkerprocessor.md)|Removes all marker processors that handle markers named  <code>attributeName</code> .|
|[GetLocalizedLineAsync(Line,CancellationToken)](/docs/api/csharp/yarn.unity.unitylocalization.unitylocalisedlineprovider.getlocalizedlineasync.md)|Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the specified <a href="yarn.line.md">Line</a> .|
|[PrepareForLinesAsync(IEnumerable<string>,CancellationToken)](/docs/api/csharp/yarn.unity.unitylocalization.unitylocalisedlineprovider.prepareforlinesasync.md)|Signals to the line provider that lines with the provided line IDs may be presented shortly.|
|[RegisterMarkerProcessor(string,IAttributeMarkerProcessor)](/docs/api/csharp/yarn.unity.unitylocalization.unitylocalisedlineprovider.registermarkerprocessor.md)|Adds a new marker processor to the line provider.|
|[Start()](/docs/api/csharp/yarn.unity.unitylocalization.unitylocalisedlineprovider.start.md)|Called by Unity when the  <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a>  has first appeared in the scene.|

## Properties

|Name|Description|
|:---|:---|
|[LocaleCode](/docs/api/csharp/yarn.unity.unitylocalization.unitylocalisedlineprovider.localecode.md)|Gets the user's current locale identifier, as a BCP-47 code.|

