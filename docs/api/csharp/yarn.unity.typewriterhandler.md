# TypewriterHandler

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`TemporalMarkupHandler`](yarn.unity.temporalmarkuphandler.md)

## Summary

A [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md) that progressively reveals the text of a line at a fixed rate of time.

```csharp
public sealed class TypewriterHandler : TemporalMarkupHandler
```

## Fields

| Name                                                                 | Description                                          |
| -------------------------------------------------------------------- | ---------------------------------------------------- |
| [lettersPerSecond](yarn.unity.typewriterhandler.letterspersecond.md) | The number of letters that will be shown per second. |
| [onCharacterTyped](yarn.unity.typewriterhandler.oncharactertyped.md) | An event that will be invoked for each               |

## Methods

| Name                                                                                                      | Description                                                                                                 |
| --------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| [OnLineDisplayComplete()](yarn.unity.typewriterhandler.onlinedisplaycomplete.md)                          | Stops the internal time counter, and finishes displaying the line.                                          |
| [OnLineTextWillAppear(MarkupParseResult,TMP\_Text)](yarn.unity.typewriterhandler.onlinetextwillappear.md) | Calculates the points in the typewriter should pause at, and starts the typewriter's internal time counter. |
| [PrepareForLine(MarkupParseResult,TMP\_Text)](yarn.unity.typewriterhandler.prepareforline.md)             | Resets the typewriter back to the initial state.                                                            |
| [PresentCharacter(int,TMP\_Text,CancellationToken)](yarn.unity.typewriterhandler.presentcharacter.md)     | Presents a single character of the line, at the appropriate point in time.                                  |
