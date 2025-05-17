# ReplacementMarkupHandler

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary


An attribute marker processor receives a marker found in a Yarn line,
and optionally rewrites the marker and its children into a new form.


```csharp
public abstract class ReplacementMarkupHandler : MonoBehaviour, IAttributeMarkerProcessor
```

## Fields

|Name|Description|
|:---|:---|
|[NoDiagnostics](/docs/api/csharp/yarn.unity.replacementmarkuphandler.nodiagnostics.md)|An empty collection of diagnostics.|

## Methods

|Name|Description|
|:---|:---|
|[ProcessReplacementMarker(MarkupAttribute,StringBuilder,List<MarkupAttribute>,string)](/docs/api/csharp/yarn.unity.replacementmarkuphandler.processreplacementmarker.md)||

## See Also

* [LineProviderBehaviour](/docs/api/csharp/yarn.unity.lineproviderbehaviour.md): A  <code>UnityEngine.MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.

