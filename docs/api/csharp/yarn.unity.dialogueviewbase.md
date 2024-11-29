# DialogueViewBase

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`AsyncDialogueViewBase`](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)

## Summary


A  <code>UnityEngine.MonoBehaviour</code>  that can present lines and options to the
user, when it receives them from a   <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .


```csharp
public abstract class DialogueViewBase : AsyncDialogueViewBase
```

## Remarks

<p>When the Dialogue Runner encounters content that the user should
see - that is, lines or options - it sends that content to all of the
dialogue views stored in <code>Yarn.Unity.DialogueRunner.dialogueViews</code>. The
Dialogue Runner then waits until all Dialogue Views have reported that
they have finished presenting the content.</p> <p>
To use this class, subclass it, and override its methods. Some of the
more common methods you may wish to override are: <a href="yarn.unity.dialogueviewbase.runline.md">RunLine(LocalizedLine,Action)</a>,
<a href="yarn.unity.dialogueviewbase.interruptline.md">InterruptLine(LocalizedLine,Action)</a>, <a href="yarn.unity.dialogueviewbase.dismissline.md">DismissLine(Action)</a> and <a href="yarn.unity.dialogueviewbase.runoptions.md">RunOptions(DialogueOption[],Action&lt;int&gt;)</a>. 
</p> <p>Once you have written your subclass, attach it as a component to a
<code>UnityEngine.GameObject</code>, and add this game object to the list of
Dialogue Views in your scene's <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>.
</p> <p>Dialogue Views do not need to handle every kind of content that
the Dialogue Runner might produce. For example, you might have one
Dialogue View that handles Lines, and another that handles Options. The
built-in <a href="yarn.unity.lineview.md">LineView</a> class is an example of this, in that it
only handles Lines and does nothing when it receives Options.</p> <p>
You may also have multiple Dialogue Views that handle the <i>same</i>
kind of content. For example, you may have a Dialogue View that receives
Lines and uses them to play voice-over audio, and a second Dialogue View
that also receives Lines and uses them to display on-screen subtitles.
</p>

## Fields

|Name|Description|
|:---|:---|
|[requestInterrupt](/docs/api/csharp/yarn.unity.dialogueviewbase.requestinterrupt.md)|Represents the method that should be called when this view wants the line to be interrupted.|

## Methods

|Name|Description|
|:---|:---|
|[DialogueComplete()](/docs/api/csharp/yarn.unity.dialogueviewbase.dialoguecomplete.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the dialogue has ended, and no more lines will be delivered.|
|[DialogueStarted()](/docs/api/csharp/yarn.unity.dialogueviewbase.dialoguestarted.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that dialogue has started.|
|[DismissLine(Action)](/docs/api/csharp/yarn.unity.dialogueviewbase.dismissline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.|
|[InterruptLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.dialogueviewbase.interruptline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.|
|[OnDialogueCompleteAsync()](/docs/api/csharp/yarn.unity.dialogueviewbase.ondialoguecompleteasync.md)||
|[OnDialogueStartedAsync()](/docs/api/csharp/yarn.unity.dialogueviewbase.ondialoguestartedasync.md)||
|[RunLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.dialogueviewbase.runline.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.|
|[RunLineAsync(LocalizedLine,LineCancellationToken)](/docs/api/csharp/yarn.unity.dialogueviewbase.runlineasync.md)||
|[RunOptions(DialogueOption[],Action<int>)](/docs/api/csharp/yarn.unity.dialogueviewbase.runoptions.md)|Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.|
|[RunOptionsAsync(DialogueOption[],CancellationToken)](/docs/api/csharp/yarn.unity.dialogueviewbase.runoptionsasync.md)||
|[UserRequestedViewAdvancement()](/docs/api/csharp/yarn.unity.dialogueviewbase.userrequestedviewadvancement.md)|Called by  <a href="yarn.unity.dialogueadvanceinput.md">DialogueAdvanceInput</a>  to signal that the user has requested that the dialogue advance.|

## See Also

* [LineProviderBehaviour](/docs/api/csharp/yarn.unity.lineproviderbehaviour.md): A  <code>UnityEngine.MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.
* Yarn.Unity.DialogueRunner.dialogueViews: 

