---
description: Learn about how to create Dialogue Views that are designed for the specific needs of your game.
---

While the Line View and Options List View are useful for lots of situations, your game might need to display lines and options in specific ways. In these situations, you can write your own custom Dialogue View, and handle the presentation of lines and options in ways that are entirely in your control.

## Creating a Dialogue View

To create a Dialogue View, you subclass the [`DialogueViewBase`](../../../api/csharp/yarn.unity.dialogueviewbase.md) class, and add it as a component to a game object in your scene. You can then add this game object to the Dialogue Views list on your scene's Dialogue Runner.

## Presenting Lines and Options

On its own, an empty subclass of `DialogueViewBase` will not do anything useful. To make it display lines and options, you'll need to implement certain methods.

To understand how to create a custom Dialogue View, it's useful to understand how the [Dialogue Runner](../dialogue-runner.md) works with content.

Yarn Spinner scripts deal in three different kinds of content: lines, options, and commands. Of these, only the first two - lines and options - are content that need to be shown directly to the player.

When the Dialogue Runner encounters lines or options, it first needs to determine the specific content the user needs to see. Once it has this, it sends the content to each of its Dialogue Views. 

{% hint style="info" %}
Your scene can have multiple Dialogue Views, and they can all do different things. It can be useful to create, for example, a Dialogue View that handles lines, and a separate Dialogue View that handles options.
{% endhint %}

### Getting Localized Content

Lines and options are represented in compiled Yarn scripts as _line IDs_. A line ID is a unique identifier for the text of a line or an option. When Yarn Spinner needs to show a line or option to the user, it asks its [Line Provider](../line-provider/README.md) to provide it with a [`LocalizedLine`](../../../api/csharp/yarn.unity.localizedline.md) object. This object contains the text of the line or option, in the user's current locale.

As discussed in [Line Providers](../line-provider/README.md), you can have different kinds of Line Providers; for example, the [Text Line Provider](../line-provider/text-line-provider.md) creates `LocalizedLine` objects that just contain text, while [Audio Line Provider](../line-provider/audio-line-provider.md) creates objects that also contain an [AudioClip](https://docs.unity3d.com/ScriptReference/AudioClip.html).

{% hint style="info" %}
When displaying a collection of options, each individual option has its own `LocalizedLine`.
{% endhint %}

Once a `LocalizedLine` has been created, the Dialogue Runner has everything that it needs to show content to the user. The next steps vary depending on whether it's showing a line or an option.

### Presenting Lines

When Yarn Spinner encounters a line of dialogue, it calls the RunLine method on each Dialogue View. This method takes two parameters: the first is the `LocalizedLine` that the Line Provider created, and the second is a [delegate](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/delegates/using-delegates) that the Dialogue View should call when the line has finished being _presented_.

In Dialogue Views, a line is _presented_ when the user has received the entire line, and is ready to move on to the next line. The practical outcome of what this means depends on the Dialogue View itself; for example, a Dialogue View that plays voice-over audio might finish presenting when all of the audio has played, while a Dialogue View that gradually reveals the text of a line might finish presenting when all of the text is visible.

The Dialogue Runner will wait until all Dialogue Views report that they've finished presenting the line. Once this happens, it moves on to the next part of the dialogue.

{% hint style="info" %}
If you're making a game where you want the dialogue to pause until the user gives a signal to proceed, your Dialogue View can pause the dialogue by not calling the completion handler until it receives the signal. Because the Dialogue Runner will wait until _all_ Dialogue Views report that they're done, the dialogue will wait.
{% endhint %}

### Interrupting Lines

At any point during a line's presentation, a Dialogue View can _interrupt_ the line. It does this by calling the [requestInterrupt](../../../api/csharp/yarn.unity.dialogueviewbase.requestinterrupt.md) method, which is a delegate that's set by its controlling Dialogue Runner. When this method is called, all Dialogue Views that have not yet finished their presentation receive a call to their [InterruptLine](../../../api/csharp/yarn.unity.dialogueviewbase.interruptline.md) method.

`InterruptLine` is very similar to `RunLine`, in that it receives a line to present and a completion handler to call when the presentation is complete. However, while `RunLine` is expected to present the line at its own pace, `InterruptLine` is a signal to finish the presentation as quickly as possible.

As before, the actual details of this depend on the Line View. To continue the examples from before, a Dialogue View that plays voice-over audio might fade out the audio over a short period of time, or even cut off playback immediately; a Dialogue View that's gradually revealing text might reveal the remaining text all at once, or rapidly reveal the remaining text.

{% hint style="warning" %}
When a Dialogue View receives a call to `InterruptLine`, it should not call the completion handler that it received from the call to `RunLine`. Calls to interrupt a line supersede calls to run a line.
{% endhint %}

Any Dialogue View may request that a line be interrupted. If multiple Dialogue Views request it, only the first request does anything.

### Dismissing Lines

When the last Dialogue View reports that its presentation is complete, either because `RunLine` finished its presentation, or because `InterruptLine` was called and it quickly finished its presentation, it needs to tell the dialogue views to get rid of the line, and potentially prepare for more content.

The Dialogue Runner does this by calling [`DismissLine`](../../../api/csharp/yarn.unity.dialogueviewbase.dismissline.md) on all Dialogue Views. As with `RunLine` and `InterruptLine` before it, `DismissLine` receives a completion handler to call when it has finished dismissing the line.

As before, the details of how a line is dismissed vary with what the Dialogue View actually does. A Dialogue View that plays voice-over audio may not need to do anything to dismiss a line, because the playback has already finished; a Dialogue View that shows line text on screen might need to hide the text, possibly with an animation.

When the last Dialogue View reports that it has finished dismissing its line, the Dialogue Runner continues running the script.

### Presenting Options

Options are slightly different to lines, in that they rely on receiving some kind of user input before the dialogue can continue: the Dialogue Runner needs to know which option was selected.

To handle options, Dialogue Views implement the [RunOptions](../../../api/csharp/yarn.unity.dialogueviewbase.runoptions.md) method. This method receives an array of [DialogueOption](../../../api/csharp/yarn.unity.dialogueoption.md) objects, each of which represents an option that can be shown to the user, as well as a completion handler.

When this method is called, the Dialogue View uses the information contained within the `DialogueOption` objects to present the choices to the player, and then awaits user input. Once it knows which option was selected, it calls the completion handler, passing in the [DialogueOptionID](../../../api/csharp/yarn.unity.dialogueoption.dialogueoptionid.md) of the selected option.

{% hint style="danger" %}
When the Dialogue Runner delivers options to its Dialogue Views, it expects exactly one of them to call the completion handler that `RunOptions` receives. 

* If _none_ of them call it, then the Dialogue Runner will never receive the option that was selected (and will wait for it forever.)
* If _more than one_ of them call it, the Dialogue Runner will throw an error.

(In most situations, you will generally only have one Dialogue View in your scene that handles options. If you have more than one, then you will need to control which one of them will call their completion handler.)
{% endhint %}

## Using Multiple Dialogue Views

Dialogue Runners can use multiple Dialogue Views. This is actually recommended, because it makes it easier to separate the code for handling lines, from that of running options.

All of the methods in [`DialogueViewBase`](../../../api/csharp/yarn.unity.dialogueviewbase.md) are optional. If you don't implement a method, then the default implementation of that method is used instead; the default implementation either does nothing, or as close to nothing as it can while still working. For example, the default implementation of `RunLine` immediately signals that presentation is complete.

* To create a Dialogue View that shows lines, implement `RunLine`, `InterruptLine` and `DismissLine`.
* To create a Dialogue View that shows options, implement `RunOptions`.
* To create a Dialogue View that supports both, implement all four.

## Responding to Dialogue Advancement Signals


During gameplay, your user may wish signal that they want to advance the dialogue: that is, they want to proceed to the next line, or they want the current line to be presented more quickly.

To handle this case, subclasses of DialogueViewBase may implement the method [`UserRequestedViewAdvancement`](../../../api/csharp/yarn.unity.lineview.userrequestedviewadvancement.md), which can be called by other parts of the gam.

In most cases, it is generally appropriate for implementations of `UserRequestedViewAdvancement` to call the [`requestInterrupt`](../../../api/csharp/yarn.unity.dialogueviewbase.requestinterrupt.md), which tells the Dialogue Runner to interrupt the line (across all views) and to proceed to the next one. However, a Dialogue View may choose to perform other actions that deliver the line more quickly.

{% hint style="info" %}
For example, in several text-based RPG games, dialogue is delivered as a text box, one letter at a time; when it's all delivered, the user can press the A button (to choose an arbitrary example) to proceed. 

If, however, you press the A button while the text is still appearing, all of the text appears all at once (as though we'd jumped ahead). 

Alternatively, if the user pressed the B button while the text was still appearing, the line would be skipped, the dialogue would move to the next line.
{% endhint %}

`UserRequestedViewAdvancement` can be called by any part of your code. Additionally, you may wish to use [`DialogueAdvanceInput`](../../../api/csharp/yarn.unity.dialogueadvanceinput.md), which is a class that listens for user input, and when it receives it, calls `UserRequestedViewAdvancement` on a view you specify.