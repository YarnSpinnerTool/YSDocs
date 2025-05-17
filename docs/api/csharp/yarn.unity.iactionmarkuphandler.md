# IActionMarkupHandler

Interface in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

## Summary


A  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a>  is an object that reacts to the
delivery of a line of dialogue, and can optionally control the timing of
that delivery.


```csharp
public interface IActionMarkupHandler
```

## Remarks

<p>
There are a number of cases where a line's delivery needs to have its
timing controlled. For example, <a href="yarn.unity.pauseeventprocessor.md">PauseEventProcessor</a> adds a
small delay between each character, creating a 'typewriter' effect as
each letter appears over time.
</p> <p>
Another example of a <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a> is an in-line
event or animation, such as causing a character to play an animation
(and waiting for that animation to complete before displaying the rest
of the line).
</p>

## Methods

|Name|Description|
|:---|:---|
|[OnCharacterWillAppear(int,MarkupParseResult,CancellationToken)](/docs/api/csharp/yarn.unity.iactionmarkuphandler.oncharacterwillappear.md)|Called repeatedly for each visible character in the line.|
|[OnLineDisplayBegin(MarkupParseResult,TMP_Text)](/docs/api/csharp/yarn.unity.iactionmarkuphandler.onlinedisplaybegin.md)|Called immediately before the first character in the line is presented.|
|[OnLineDisplayComplete()](/docs/api/csharp/yarn.unity.iactionmarkuphandler.onlinedisplaycomplete.md)|Called after the last call to  <code>PresentCharacter(int,     TMP_Text, CancellationToken)</code> .|
|[OnLineWillDismiss()](/docs/api/csharp/yarn.unity.iactionmarkuphandler.onlinewilldismiss.md)|Called right before the line will dismiss itself.|
|[OnPrepareForLine(MarkupParseResult,TMP_Text)](/docs/api/csharp/yarn.unity.iactionmarkuphandler.onprepareforline.md)|Called when the line view receives the line, to prepare for showing the line.|

