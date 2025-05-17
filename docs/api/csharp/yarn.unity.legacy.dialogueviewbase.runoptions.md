# DialogueViewBase.RunOptions(DialogueOption[],Action<int>)

Method in [DialogueViewBase](/docs/api/csharp/yarn.unity.legacy.dialogueviewbase.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of
options should be displayed to the user.


```csharp
public virtual void RunOptions(DialogueOption[] dialogueOptions, Action<int> onOptionSelected)
```

## Remarks

<p>This method is called when the Dialogue Runner wants to show a
collection of options that the user should choose from. Each option
is represented by a <a href="yarn.unity.dialogueoption.md">DialogueOption</a> object, which
contains information about the option.</p> <p>When this method is called, the Dialogue View should display
appropriate user interface elements that let the user choose among
the options.</p> <p>After this method is called, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>
will wait until the `onOptionSelected` method is
called.</p> <p>After calling the `onOptionSelected` method, the
Dialogue View should dismiss whatever options UI it presented. The
Dialogue Runner will immediately deliver the next piece of content.
</p> <p>
{% hint style="warning" %}
When the Dialogue Runner delivers Options to
its Dialogue Views, it expects precisely one of its views to call
the `onOptionSelected` method.
<ul type="bullet"><li>
If your scene includes <b>no</b> dialogue views that override <a href="yarn.unity.legacy.dialogueviewbase.runoptions.md">RunOptions(DialogueOption[],Action&lt;int&gt;)</a>, the Dialogue Runner will never be told which
option the user selected, and will therefore wait forever.
</li><li>
If your scene includes <b>multiple</b> dialogue views that override
<a href="yarn.unity.legacy.dialogueviewbase.runoptions.md">RunOptions(DialogueOption[],Action&lt;int&gt;)</a>, they will all receive a call each time the
dialogue system presents options to the player. You must ensure that
only one of them calls the `onOptionSelected`
method.
</li></ul>
{% endhint %}
</p> <p>
{% hint style="note" %}

The default implementation of this method does nothing, and does not
call the `onOptionSelected` method (that is, it
ignores any Options it receives.)

{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.DialogueOption\[\]](/docs/api/csharp/yarn.unity.dialogueoption.md) dialogueOptions|The set of options that should be displayed to the user.|
|`Action<int>` onOptionSelected|A method that should be called when the user has made a selection.|

