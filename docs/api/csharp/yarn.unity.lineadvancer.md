# LineAdvancer

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`DialoguePresenterBase`](/docs/api/csharp/yarn.unity.dialoguepresenterbase.md)

## Summary


A dialogue presenter that listens for user input and sends requests to a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to advance the presentation of the current line,
either by asking a dialogue runner to hurry up its delivery, advance to
the next line, or cancel the entire dialogue session.


```csharp
public sealed class LineAdvancer : DialoguePresenterBase, IActionMarkupHandler
```

## Enums

|Name|Description|
|:---|:---|
|[InputMode](/docs/api/csharp/yarn.unity.lineadvancer.inputmode.md)|The type of input that this line advancer responds to.|

## Fields

|Name|Description|
|:---|:---|
|[advanceRequestsBeforeCancellingLine](/docs/api/csharp/yarn.unity.lineadvancer.advancerequestsbeforecancellingline.md)|The number of times that a 'hurry up' signal occurs before the line advancer requests that the next line be shown.|
|[multiAdvanceIsCancel](/docs/api/csharp/yarn.unity.lineadvancer.multiadvanceiscancel.md)|If  `true` , repeatedly signalling that the line should be hurried up will cause the line advancer to request that the next line be shown.|

## Methods

|Name|Description|
|:---|:---|
|[OnCharacterWillAppear(int,MarkupParseResult,CancellationToken)](/docs/api/csharp/yarn.unity.lineadvancer.oncharacterwillappear.md)||
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.lineadvancer.ondialoguecompleteasync.md)|Called by a dialogue runner when dialogue ends to remove the input action handlers.|
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.lineadvancer.ondialoguestartedasync.md)|Called by a dialogue runner when dialogue starts to add input action handlers for advancing the line.|
|[OnLineDisplayBegin(MarkupParseResult,TMP_Text)](/docs/api/csharp/yarn.unity.lineadvancer.onlinedisplaybegin.md)||
|[OnLineDisplayComplete()](/docs/api/csharp/yarn.unity.lineadvancer.onlinedisplaycomplete.md)||
|[OnLineWillDismiss()](/docs/api/csharp/yarn.unity.lineadvancer.onlinewilldismiss.md)||
|[OnPrepareForLine(MarkupParseResult,TMP_Text)](/docs/api/csharp/yarn.unity.lineadvancer.onprepareforline.md)||
|[RequestDialogueCancellation()](/docs/api/csharp/yarn.unity.lineadvancer.requestdialoguecancellation.md)|Requests that the dialogue runner to instruct all line views to dismiss their content, and then stops the dialogue.|
|[RequestLineHurryUp()](/docs/api/csharp/yarn.unity.lineadvancer.requestlinehurryup.md)|Requests that the line be hurried up.|
|[RequestNextLine()](/docs/api/csharp/yarn.unity.lineadvancer.requestnextline.md)|Requests that the dialogue runner proceeds to the next line.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.lineadvancer.runlineasync.md)|Called by a dialogue view to signal that a line is running.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.lineadvancer.runoptionsasync.md)|Called by a dialogue view to signal that options are running.|

