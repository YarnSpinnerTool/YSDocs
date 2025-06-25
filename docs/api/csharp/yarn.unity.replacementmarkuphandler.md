# ReplacementMarkupHandler

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary

An attribute marker processor receives a marker found in a Yarn line,\
and optionally rewrites the marker and its children into a new form.

```csharp
public abstract class ReplacementMarkupHandler : MonoBehaviour, IAttributeMarkerProcessor
```

## Fields

| Name                                                                  | Description                         |
| --------------------------------------------------------------------- | ----------------------------------- |
| [NoDiagnostics](yarn.unity.replacementmarkuphandler.nodiagnostics.md) | An empty collection of diagnostics. |

## Methods

| Name                                                                                                                                   | Description |
| -------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| [ProcessReplacementMarker(MarkupAttribute,StringBuilder,List,string)](yarn.unity.replacementmarkuphandler.processreplacementmarker.md) |             |

## See Also

* [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md): A `UnityEngine.MonoBehaviour` that produces [LocalizedLine](yarn.unity.localizedline.md) s, for use in Dialogue Presenters.
