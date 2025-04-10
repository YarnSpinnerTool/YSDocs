# RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [AsyncOptionsView](yarn.unity.asyncoptionsview.md)

## Summary

Called by a [DialogueRunner](yarn.unity.dialoguerunner.md) when a line needs to be presented, and stores the line as the 'last seen line' so that it can be shown when options appear.

```csharp
public override YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Remarks

This view does not display lines directly, but instead stores lines so that when options are run, the last line that ran before the options appeared can be shown.

## Parameters

| Name                                                                          | Description                                                                                                                                                                              |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Unity.LocalizedLine](yarn.unity.localizedline.md) line                  | The line to present.                                                                                                                                                                     |
| [Yarn.Unity.LineCancellationToken](yarn.unity.linecancellationtoken.md) token | A [LineCancellationToken](yarn.unity.linecancellationtoken.md) that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line. |

## Returns

A completed task.
