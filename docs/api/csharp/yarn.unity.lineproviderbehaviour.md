# LineProviderBehaviour

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary

A `UnityEngine.MonoBehaviour` that produces [LocalizedLine](yarn.unity.localizedline.md) s, for use in Dialogue Views.

```csharp
public abstract class LineProviderBehaviour : MonoBehaviour
```

## Remarks

[DialogueRunner](yarn.unity.dialoguerunner.md)s use a [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md) to get [LocalizedLine](yarn.unity.localizedline.md)s, which contain the localized information that [DialogueViewBase](yarn.unity.dialogueviewbase.md) classes use to present content to the player.

Subclasses of this abstract class may return subclasses of [LocalizedLine](yarn.unity.localizedline.md). For example, [AudioLineProvider](yarn.unity.audiolineprovider.md) returns an `AudioLocalizedLine`, which includes `UnityEngine.AudioClip`; views that make use of audio can then access this additional data.

## Methods

| Name                                                                                | Description                                                                                                            |
| ----------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| [GetLocalizedLine(Yarn.Line)](yarn.unity.lineproviderbehaviour.getlocalizedline.md) | Prepares and returns a [LocalizedLine](yarn.unity.localizedline.md) from the specified [Line](yarn.line.md) .          |
| [PrepareForLines(IEnumerable)](yarn.unity.lineproviderbehaviour.prepareforlines.md) | Signals to the line provider that lines with the provided line IDs may be presented shortly.                           |
| [Start()](yarn.unity.lineproviderbehaviour.start.md)                                | Called by Unity when the [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md) has first appeared in the scene. |

## Properties

| Name                                                                 | Description                                                                                                                                                              |
| -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [LinesAvailable](yarn.unity.lineproviderbehaviour.linesavailable.md) | Gets a value indicating whether this line provider is ready to provide [LocalizedLine](yarn.unity.localizedline.md) objects. The default implementation returns `true` . |
| [LocaleCode](yarn.unity.lineproviderbehaviour.localecode.md)         | Gets the user's current locale identifier, as a BCP-47 code.                                                                                                             |
| [YarnProject](yarn.unity.lineproviderbehaviour.yarnproject.md)       |                                                                                                                                                                          |

## See Also

* [DialogueViewBase](yarn.unity.dialogueviewbase.md): A `UnityEngine.MonoBehaviour` that can present lines and options to the user, when it receives them from a [DialogueRunner](yarn.unity.dialoguerunner.md) .
