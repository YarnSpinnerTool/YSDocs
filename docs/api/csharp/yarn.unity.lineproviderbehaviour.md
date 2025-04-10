# LineProviderBehaviour

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary

A `UnityEngine.MonoBehaviour` that produces [LocalizedLine](yarn.unity.localizedline.md) s, for use in Dialogue Views.

```csharp
public abstract class LineProviderBehaviour : MonoBehaviour, ILineProvider
```

## Remarks

[DialogueRunner](yarn.unity.dialoguerunner.md) s use a [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md) to get [LocalizedLine](yarn.unity.localizedline.md) s, which contain the localized information that is presented to the player through dialogue views.

## Methods

| Name                                                                                                                     | Description                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| [DeregisterMarkerProcessor(string)](yarn.unity.lineproviderbehaviour.deregistermarkerprocessor.md)                       | Removes all marker processors that handle markers named `attributeName` .                                              |
| [GetLocalizedLineAsync(Line,CancellationToken)](yarn.unity.lineproviderbehaviour.getlocalizedlineasync.md)               | Prepares and returns a [LocalizedLine](yarn.unity.localizedline.md) from the specified [Line](yarn.line.md) .          |
| [PrepareForLinesAsync(IEnumerable,CancellationToken)](yarn.unity.lineproviderbehaviour.prepareforlinesasync.md)          | Signals to the line provider that lines with the provided line IDs may be presented shortly.                           |
| [RegisterMarkerProcessor(string,IAttributeMarkerProcessor)](yarn.unity.lineproviderbehaviour.registermarkerprocessor.md) | Adds a new marker processor to the line provider.                                                                      |
| [Start()](yarn.unity.lineproviderbehaviour.start.md)                                                                     | Called by Unity when the [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md) has first appeared in the scene. |

## Properties

| Name                                                                 | Description                                                                                 |
| -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [LinesAvailable](yarn.unity.lineproviderbehaviour.linesavailable.md) |                                                                                             |
| [LocaleCode](yarn.unity.lineproviderbehaviour.localecode.md)         | Gets the user's current locale identifier, as a BCP-47 code.                                |
| [YarnProject](yarn.unity.lineproviderbehaviour.yarnproject.md)       | The [YarnProject](ilineprovider.yarnproject.md) that contains the localized data for lines. |

## See Also

* [DialogueViewBase](yarn.unity.dialogueviewbase.md): Implements the Yarn Spinner 2 callback-based API for dialogue views using Yarn Spinner 3.
