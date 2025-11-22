# IActionMarkupHandler

Interface in [Yarn.Unity](yarn.unity.md)

## Summary

A [IActionMarkupHandler](yarn.unity.iactionmarkuphandler.md) is an object that reacts to the\
delivery of a line of dialogue, and can optionally control the timing of\
that delivery.

```csharp
public interface IActionMarkupHandler
```

## Remarks

There are a number of cases where a line's delivery needs to have its\
timing controlled. For example, [PauseEventProcessor](yarn.unity.pauseeventprocessor.md) adds a\
small delay between each character, creating a 'typewriter' effect as\
each letter appears over time.

Another example of a [IActionMarkupHandler](yarn.unity.iactionmarkuphandler.md) is an in-line\
event or animation, such as causing a character to play an animation\
(and waiting for that animation to complete before displaying the rest\
of the line).

## Methods

| Name                                                                                                                       | Description                                                                          |
| -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| [OnCharacterWillAppear(int,MarkupParseResult,CancellationToken)](yarn.unity.iactionmarkuphandler.oncharacterwillappear.md) | Called repeatedly for each visible character in the line.                            |
| [OnLineDisplayBegin(MarkupParseResult,TMP\_Text)](yarn.unity.iactionmarkuphandler.onlinedisplaybegin.md)                   | Called immediately before the first character in the line is presented.              |
| [OnLineDisplayComplete()](yarn.unity.iactionmarkuphandler.onlinedisplaycomplete.md)                                        | Called after the last call to `PresentCharacter(int, TMP_Text, CancellationToken)` . |
| [OnLineWillDismiss()](yarn.unity.iactionmarkuphandler.onlinewilldismiss.md)                                                | Called right before the line will dismiss itself.                                    |
| [OnPrepareForLine(MarkupParseResult,TMP\_Text)](yarn.unity.iactionmarkuphandler.onprepareforline.md)                       | Called when the line view receives the line, to prepare for showing the line.        |
