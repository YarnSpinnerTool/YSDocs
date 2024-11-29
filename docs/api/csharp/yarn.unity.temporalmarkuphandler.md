# TemporalMarkupHandler

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary


A  <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a>  is an object that reacts to the
delivery of a line of dialogue, and can optionally control the timing of
that delivery.


```csharp
public abstract class TemporalMarkupHandler : MonoBehaviour
```

## Remarks

<p>
There are a number of cases where a line's delivery needs to have its
timing controlled. For example, <a href="yarn.unity.typewriterhandler.md">TypewriterHandler</a> adds a
small delay between each character, creating a 'typewriter' effect as
each letter appears over time.
</p> <p>
Another example of a <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a> is an in-line
event or animation, such as causing a character to play an animation
(and waiting for that animation to complete before displaying the rest
of the line).
</p>

## Methods

|Name|Description|
|:---|:---|
|[OnLineDisplayComplete()](/docs/api/csharp/yarn.unity.temporalmarkuphandler.onlinedisplaycomplete.md)|Called after the last call to  <a href="yarn.unity.temporalmarkuphandler.presentcharacter.md">PresentCharacter(int,TMP_Text,CancellationToken)</a> .|
|[OnLineTextWillAppear(MarkupParseResult,TMP_Text)](/docs/api/csharp/yarn.unity.temporalmarkuphandler.onlinetextwillappear.md)|Called immediately before the first character in the line is presented.|
|[PrepareForLine(MarkupParseResult,TMP_Text)](/docs/api/csharp/yarn.unity.temporalmarkuphandler.prepareforline.md)|Called when the line view receives the line, to prepare for showing the line.|
|[PresentCharacter(int,TMP_Text,CancellationToken)](/docs/api/csharp/yarn.unity.temporalmarkuphandler.presentcharacter.md)|Called repeatedly for each visible character in the line.|

