# LineProviderBehaviour

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `MonoBehaviour`

## Summary


A  <code>MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.


```csharp
public abstract class LineProviderBehaviour : MonoBehaviour
```

## Remarks

<p>
<a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>s use a <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a> to get <a href="yarn.unity.localizedline.md">LocalizedLine</a>s,
which contain the localized information that <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a> classes use to present content to the
player. 
</p> <p>
Subclasses of this abstract class may return subclasses of <a href="yarn.unity.localizedline.md">LocalizedLine</a>. For example, <a href="yarn.unity.audiolineprovider.md">AudioLineProvider</a> returns an <a href="yarn.unity.audiolocalizedline.md">AudioLocalizedLine</a>, which includes <code>AudioClip</code>; views that make use of audio can then access
this additional data.
</p>

## Fields

|Name|Description|
|:---|:---|
|[textLanguageCode](/api/csharp/yarn.unity.lineproviderbehaviour.textlanguagecode.md)||

## Methods

|Name|Description|
|:---|:---|
|[GetLocalizedLine(Yarn.Line)](/api/csharp/yarn.unity.lineproviderbehaviour.getlocalizedline.md)|Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the specified  <code>Yarn.Line</code> .|
|[PrepareForLines(IEnumerable<string>)](/api/csharp/yarn.unity.lineproviderbehaviour.prepareforlines.md)|Signals to the line provider that lines with the provided line IDs may be presented shortly.|
|[Start()](/api/csharp/yarn.unity.lineproviderbehaviour.start.md)|Called by Unity when the  <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a>  has first appeared in the scene.|

## Properties

|Name|Description|
|:---|:---|
|[LinesAvailable](/api/csharp/yarn.unity.lineproviderbehaviour.linesavailable.md)|Gets a value indicating whether this line provider is ready to provide  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  objects. The default implementation returns  <code>true</code> .|
|[YarnProject](/api/csharp/yarn.unity.lineproviderbehaviour.yarnproject.md)||

## See Also

* [DialogueViewBase](/api/csharp/yarn.unity.dialogueviewbase.md): A  <code>MonoBehaviour</code>  that can present lines and options to the user, when it receives them from a   <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .

