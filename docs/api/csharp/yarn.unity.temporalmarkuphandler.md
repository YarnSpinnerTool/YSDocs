# TemporalMarkupHandler

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary

A [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md) is an object that reacts to the delivery of a line of dialogue, and can optionally control the timing of that delivery.

```csharp
public abstract class TemporalMarkupHandler : MonoBehaviour
```

## Remarks

There are a number of cases where a line's delivery needs to have its timing controlled. For example, [TypewriterHandler](yarn.unity.typewriterhandler.md) adds a small delay between each character, creating a 'typewriter' effect as each letter appears over time.

Another example of a [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md) is an in-line event or animation, such as causing a character to play an animation (and waiting for that animation to complete before displaying the rest of the line).

## Methods

| Name                                                                                                          | Description                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| [OnLineDisplayComplete()](yarn.unity.temporalmarkuphandler.onlinedisplaycomplete.md)                          | Called after the last call to [PresentCharacter(int,TMP\_Text,CancellationToken)](yarn.unity.temporalmarkuphandler.presentcharacter.md) . |
| [OnLineTextWillAppear(MarkupParseResult,TMP\_Text)](yarn.unity.temporalmarkuphandler.onlinetextwillappear.md) | Called immediately before the first character in the line is presented.                                                                   |
| [PrepareForLine(MarkupParseResult,TMP\_Text)](yarn.unity.temporalmarkuphandler.prepareforline.md)             | Called when the line view receives the line, to prepare for showing the line.                                                             |
| [PresentCharacter(int,TMP\_Text,CancellationToken)](yarn.unity.temporalmarkuphandler.presentcharacter.md)     | Called repeatedly for each visible character in the line.                                                                                 |
