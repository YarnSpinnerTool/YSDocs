# TemporalMarkupHandler.PresentCharacter(int,TMP_Text,CancellationToken)

Method in [TemporalMarkupHandler](/docs/api/csharp/yarn.unity.temporalmarkuphandler.md)

## Summary


Called repeatedly for each visible character in the line.


```csharp
public abstract YarnTask PresentCharacter(int currentCharacterIndex, TMP_Text text, CancellationToken cancellationToken);
```

## Remarks

This method is a  <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a> 
object's main opportunity to take action during line
display.

## Parameters

|Name|Description|
|:---|:---|
|`int` currentCharacterIndex|The zero-based index of the character being displayed.|
|`TMPro.TMP_Text` text|A  <code>TMPro.TMP_Text</code>  object that the line is being displayed in.|
|`System.Threading.CancellationToken` cancellationToken|A cancellation token representing whether the|

## Returns

A task that completes when the  <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a>  has completed presenting this
character. Dialogue views will wait until this task is complete
before displaying the remainder of the line.

