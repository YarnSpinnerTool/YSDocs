# LineProviderBehaviour

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary


A  <code>UnityEngine.MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.


```csharp
public abstract class LineProviderBehaviour : MonoBehaviour
```

## Remarks

<p>
<a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>s use a <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a> to get <a href="yarn.unity.localizedline.md">LocalizedLine</a>s,
which contain the localized information that <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a> classes use to present content to the
player. 
</p> <p>
Subclasses of this abstract class may return subclasses of <a href="yarn.unity.localizedline.md">LocalizedLine</a>. For example, <a href="yarn.unity.audiolineprovider.md">AudioLineProvider</a> returns an <code>AudioLocalizedLine</code>, which includes <code>UnityEngine.AudioClip</code>; views that make use of audio can then access
this additional data.
</p>

## Methods

|Name|Description|
|:---|:---|
|[GetLocalizedLine(Yarn.Line)](/api/csharp/yarn.unity.lineproviderbehaviour.getlocalizedline.md)|Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the specified  <a href="yarn.line.md">Line</a> .|
|[PrepareForLines(IEnumerable<string>)](/api/csharp/yarn.unity.lineproviderbehaviour.prepareforlines.md)|Signals to the line provider that lines with the provided line IDs may be presented shortly.|
|[Start()](/api/csharp/yarn.unity.lineproviderbehaviour.start.md)|Called by Unity when the  <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a>  has first appeared in the scene.|

## Properties

|Name|Description|
|:---|:---|
|[LinesAvailable](/api/csharp/yarn.unity.lineproviderbehaviour.linesavailable.md)|Gets a value indicating whether this line provider is ready to provide  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  objects. The default implementation returns  <code>true</code> .|
|[LocaleCode](/api/csharp/yarn.unity.lineproviderbehaviour.localecode.md)|Gets the user's current locale identifier, as a BCP-47 code.|
|[YarnProject](/api/csharp/yarn.unity.lineproviderbehaviour.yarnproject.md)||

## See Also

* [DialogueViewBase](/api/csharp/yarn.unity.dialogueviewbase.md): A  <code>UnityEngine.MonoBehaviour</code>  that can present lines and options to the user, when it receives them from a   <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .

