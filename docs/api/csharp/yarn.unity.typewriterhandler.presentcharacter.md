# TypewriterHandler.PresentCharacter(int,TMP_Text,CancellationToken)

Method in [TypewriterHandler](/docs/api/csharp/yarn.unity.typewriterhandler.md)

## Summary


Presents a single character of the line, at the appropriate point in
time.


```csharp
public override async YarnTask PresentCharacter(int currentCharacterIndex, TMP_Text text, CancellationToken cancellationToken)
```

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

