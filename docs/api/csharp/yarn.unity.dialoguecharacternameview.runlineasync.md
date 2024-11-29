# DialogueCharacterNameView.RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [DialogueCharacterNameView](/docs/api/csharp/yarn.unity.dialoguecharacternameview.md)

## Summary


Invokes the  <a href="yarn.unity.dialoguecharacternameview.onnameupdate.md">onNameUpdate</a>  or  <a href="yarn.unity.dialoguecharacternameview.onnamenotpresent.md">onNameNotPresent</a>  events, depending on the contents of
<code>line</code> .


```csharp
public override YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) line|The line to present.|
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) token|A  <a href="yarn.unity.linecancellationtoken.md">LineCancellationToken</a>  that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line.|

## Returns

A task that completes when the dialogue view has finished
showing the line to the user.

