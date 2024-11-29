# AsyncOptionsView.RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [AsyncOptionsView](/docs/api/csharp/yarn.unity.asyncoptionsview.md)

## Summary


Called by a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  when a line needs to be
presented, and stores the line as the 'last seen line' so that it
can be shown when options appear.


```csharp
public override YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Remarks

This view does not display lines directly, but instead
stores lines so that when options are run, the last line that ran
before the options appeared can be shown.

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) line|The line to present.|
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) token|A  <a href="yarn.unity.linecancellationtoken.md">LineCancellationToken</a>  that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line.|

## Returns

A completed task.

