# Effects

Class in [Yarn.Unity](../)

Inherits from `System.Object`

## Summary

Contains coroutine methods that apply visual effects. This class is used by [LineView](../yarn.unity.lineview/) to handle animating the presentation of lines.

```csharp
public static class Effects
```

## Classes

| Name                                                                   | Description                                                                         |
| ---------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [CoroutineInterruptToken](yarn.unity.effects.coroutineinterrupttoken/) | An object that can be used to signal to a coroutine that it should terminate early. |

## Methods

| Name                                                                                                                                                                     | Description                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FadeAlpha(CanvasGroup,float,float,float,CoroutineInterruptToken)](yarn.unity.effects.fadealpha.md)                                                                      | A coroutine that fades a `UnityEngine.CanvasGroup` object's opacity from `from` to `to` over the course of `fadeTime` seconds, and then invokes `onComplete` . |
| [PausableTypewriter(TextMeshProUGUI,float,Action,Action,Action,Stack<(int position, float duration)>,CoroutineInterruptToken)](yarn.unity.effects.pausabletypewriter.md) | A coroutine that gradually reveals the text in a `TMPro.TextMeshProUGUI` object over time.                                                                     |
| [Typewriter(TextMeshProUGUI,float,Action,CoroutineInterruptToken)](yarn.unity.effects.typewriter.md)                                                                     | A coroutine that gradually reveals the text in a `TMPro.TextMeshProUGUI` object over time.                                                                     |
