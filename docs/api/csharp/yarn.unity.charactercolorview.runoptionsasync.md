# CharacterColorView.RunOptionsAsync(DialogueOption[],CancellationToken)

Method in [CharacterColorView](/docs/api/csharp/yarn.unity.charactercolorview.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of
options should be displayed to the user.


```csharp
public override YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken)
```

## Remarks

<p>This method is called when the Dialogue Runner wants to show a
collection of options that the user should choose from. Each option
is represented by a <a href="yarn.unity.dialogueoption.md">DialogueOption</a> object, which
contains information about the option.</p> <p>When this method is called, the Dialogue View should display
appropriate user interface elements that let the user choose among
the options.</p> <p>This method should await until an option is selected, and then
return the selected option. If this view doesn't handle options, or
is otherwise unable to select an option, it should return <code>YarnAsync.NoOptionSelected</code>. The dialogue runner will wait
for all dialogue views to return, so if a dialogue view doesn't or
can't handle options, it's good practice to return as soon as
possible. 
</p> <p>If the <code>cancellationToken</code> becomes cancelled,
this means that the dialogue runner no longer needs this dialogue
view to make a selection, and this method should return as soon as
possible; its return value will not be used.
</p> <p>
{% hint style="note" %}

The default implementation of this method returns <code>YarnAsync.NoOptionSelected</code>. 

{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.DialogueOption\[\]](/docs/api/csharp/yarn.unity.dialogueoption.md) dialogueOptions|The set of options that should be displayed to the user.|
|`CancellationToken` cancellationToken|A  <code>System.Threading.CancellationToken</code>  that becomes cancelled when the dialogue runner no longer needs this dialogue view to return an option.|

## Returns

A task that indicates which option was selected, or that this dialogue view did not select an option.

## See Also

* [AsyncDialogueViewBase.RunLineAsync\(LocalizedLine,LineCancellationToken\)](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.runlineasync.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.
* YarnAsync.NoOptionSelected
