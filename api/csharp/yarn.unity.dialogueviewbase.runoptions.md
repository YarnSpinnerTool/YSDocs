# DialogueViewBase.RunOptions(DialogueOption[],Action<int>)

Method in [DialogueViewBase](/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set
of options should be displayed to the user.


```csharp
public virtual void RunOptions(DialogueOption[] dialogueOptions, Action<int> onOptionSelected)
```

## Remarks

<p>When this method is called, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will pause execution until the
`onOptionSelected` method is called.</p> <p>If your scene includes multiple dialogue views that
override this method, they will all receive a call each time
the dialogue system presents options to the player. You must
ensure that only one of them calls the <code>onOptionSelected</code> method.</p>

## Parameters

|Name|Description|
|:---|:---|
|dialogueOptions|The set of options that should be displayed to the user.|
|onOptionSelected|A method that should be called when the user has made a selection.|

## Returns



