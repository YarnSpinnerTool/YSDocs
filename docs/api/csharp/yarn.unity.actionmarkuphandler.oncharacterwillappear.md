# ActionMarkupHandler.OnCharacterWillAppear(int,MarkupParseResult,CancellationToken)

Method in [ActionMarkupHandler](/docs/api/csharp/yarn.unity.actionmarkuphandler.md)

## Summary


Called repeatedly for each visible character in the line.


```csharp
public abstract YarnTask OnCharacterWillAppear(int currentCharacterIndex, MarkupParseResult line, CancellationToken cancellationToken);
```

## Remarks

This method is a  <a href="yarn.unity.actionmarkuphandler.md">ActionMarkupHandler</a> 
object's main opportunity to take action during line
display.

## Parameters

|Name|Description|
|:---|:---|
|`int` currentCharacterIndex|The zero-based index of the character being displayed.|
| text|A  `TMPro.TMP_Text`  object that the line is being displayed in.|
|`CancellationToken` cancellationToken|A cancellation token representing whether the|
|[MarkupParseResult](/docs/api/csharp/yarn.markup.markupparseresult.md) line||

## Returns

A task that completes when the  <a href="yarn.unity.actionmarkuphandler.md">ActionMarkupHandler</a>  has completed presenting this
character. Dialogue views will wait until this task is complete
before displaying the remainder of the line.

