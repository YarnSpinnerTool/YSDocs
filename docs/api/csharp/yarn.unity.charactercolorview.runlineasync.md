# CharacterColorView.RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [CharacterColorView](/docs/api/csharp/yarn.unity.charactercolorview.md)

## Summary


Updates the text colour of  <code>Yarn.Unity.CharacterColorView.lineTexts</code>  based on the
character name of  <code>line</code> , if any.


```csharp
public override YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Remarks

If the line doesn't have a character name, or if the
character name is not found in  <code>Yarn.Unity.CharacterColorView.colorData</code> ,  <code>Yarn.Unity.CharacterColorView.defaultColor</code>  is used.

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) line|The line to present.|
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) token|A  <a href="yarn.unity.linecancellationtoken.md">LineCancellationToken</a>  that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line.|

## Returns

A task that completes when the dialogue view has finished
showing the line to the user.

