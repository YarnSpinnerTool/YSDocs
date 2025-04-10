# UnityLocalisedLineProvider

Class in [Yarn.Unity.UnityLocalization](yarn.unity.unitylocalization.md)

Inherits from [`LineProviderBehaviour`](yarn.unity.lineproviderbehaviour.md)

## Summary

A line provider that uses the Unity Localization system to get localized content for Yarn lines.

```csharp
public class UnityLocalisedLineProvider : LineProviderBehaviour
```

## Methods

| Name                                                                                                                                            | Description                                                                                                            |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| [DeregisterMarkerProcessor(string)](yarn.unity.unitylocalization.unitylocalisedlineprovider.deregistermarkerprocessor.md)                       | Removes all marker processors that handle markers named `attributeName` .                                              |
| [GetLocalizedLineAsync(Line,CancellationToken)](yarn.unity.unitylocalization.unitylocalisedlineprovider.getlocalizedlineasync.md)               | Prepares and returns a [LocalizedLine](yarn.unity.localizedline.md) from the specified [Line](yarn.line.md) .          |
| [PrepareForLinesAsync(IEnumerable,CancellationToken)](yarn.unity.unitylocalization.unitylocalisedlineprovider.prepareforlinesasync.md)          | Signals to the line provider that lines with the provided line IDs may be presented shortly.                           |
| [RegisterMarkerProcessor(string,IAttributeMarkerProcessor)](yarn.unity.unitylocalization.unitylocalisedlineprovider.registermarkerprocessor.md) | Adds a new marker processor to the line provider.                                                                      |
| [Start()](yarn.unity.unitylocalization.unitylocalisedlineprovider.start.md)                                                                     | Called by Unity when the [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md) has first appeared in the scene. |

## Properties

| Name                                                                                | Description                                                  |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| [LocaleCode](yarn.unity.unitylocalization.unitylocalisedlineprovider.localecode.md) | Gets the user's current locale identifier, as a BCP-47 code. |
