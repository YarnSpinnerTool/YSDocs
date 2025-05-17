# DialogueRunner.GetPauseDurationsInsideLine(Markup.MarkupParseResult)

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Creates a stack of typewriter pauses to use to temporarily halt the
typewriter effect.


```csharp
public static Stack<(int position, float duration)> GetPauseDurationsInsideLine(Markup.MarkupParseResult line)
```

## Remarks


This is intended to be used in conjunction with the  [PausableTypewriter(TextMeshProUGUI,float,Action?,Action?,Action?,Stack&lt;(int position, float duration)&gt;?,CoroutineInterruptToken?)](yarn.unity.effects.pausabletypewriter.md)  effect. The stack of tuples
created are how the typewriter effect knows when, and for how long,
to halt the effect.
<p>
The pause duration property is in milliseconds but all the effects
code assumes seconds So here we will be dividing it by 1000 to make
sure they interconnect correctly.
</p>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupParseResult](/docs/api/csharp/yarn.markup.markupparseresult.md) line|The line from which we covet the pauses|

## Returns

A stack of positions and duration pause tuples from within
the line

