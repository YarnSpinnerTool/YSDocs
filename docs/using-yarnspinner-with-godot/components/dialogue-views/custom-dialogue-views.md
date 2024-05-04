---
description: Learn how to create Dialogue Views that are designed for the specific needs of your game.
---

While the Line View and Options List View are useful for lots of situations, your game might need to display lines and options in specific ways. In these situations, you can write your own custom Dialogue View, and handle the presentation of lines and options in ways that are entirely in your control.

## Creating a Dialogue View

To create a Dialogue View, you write a script that implements the `DialogueViewBase` interface, and add your script to a node in your scene. You can then add this node to the Dialogue Views list on your scene's Dialogue Runner.

## Presenting Lines and Options

On its own, an empty script implementing the `DialogueViewBase` interface will not do anything useful. To make it display lines and options, you'll need to implement certain methods.

To understand how to create a custom Dialogue View, it's useful to understand how the [Dialogue Runner](../dialogue-runner.md) works with content.

Yarn Spinner scripts deal in three different kinds of content: lines, options, and commands. Of these, only the first two - lines and options - are content that need to be shown directly to the player.

When the Dialogue Runner encounters lines or options, it first needs to determine the specific content the user needs to see. Once it has this, it sends the content to each of its Dialogue Views. 

{% hint style="info" %}
Your scene can have multiple Dialogue Views, and they can all do different things. It can be useful to create, for example, a Dialogue View that handles lines, and a separate Dialogue View that handles options.
{% endhint %}

### Getting Localized Content

Lines and options are represented in compiled Yarn scripts as _line IDs_. A line ID is a unique identifier for the text of a line or an option. When Yarn Spinner needs to show a line or option to the user, it asks its [Line Provider](../line-provider/README.md) to provide it with a `LocalizedLine`]object. This object contains the text of the line or option, in the user's current locale.

The [Text Line Provider](../line-provider/text-line-provider.md) provided with the plugin creates `LocalizedLine` objects for views to display.

{% hint style="info" %}
When displaying a collection of options, each individual option has its own `LocalizedLine`.
{% endhint %}

Once a `LocalizedLine` has been created, the Dialogue Runner has everything that it needs to show content to the user. The next steps vary depending on whether it's showing a line or an option.

### Presenting Lines

When Yarn Spinner encounters a line of dialogue, it calls the RunLine method on each Dialogue View. This method takes two parameters: the first is the `LocalizedLine` that the Line Provider created, and the second is a [delegate](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/delegates/using-delegates) that the Dialogue View should call when the line has finished being _presented_.

In Dialogue Views, a line is _presented_ when the user has received the entire line, and is ready to move on to the next line. The practical outcome of what this means depends on the Dialogue View itself; for example, a Dialogue View that plays voice-over audio might finish presenting when all of the audio has played, while a Dialogue View that gradually reveals the text of a line might finish presenting when all of the text is visible.

The Dialogue Runner will wait until all Dialogue Views report that they've finished presenting the line. Once this happens, it moves on to the next part of the dialogue.

{% hint style="info" %}
If you're making a game where you want the dialogue to pause until the user takes an action to proceed, your Dialogue View can pause the dialogue by not calling the completion handler until it receives the signal. Because the Dialogue Runner will wait until _all_ Dialogue Views report that they're done, the dialogue will wait until your view tells it to continue.
{% endhint %}

### Interrupting Lines

At any point during a line's presentation, a Dialogue View can _interrupt_ the line. It does this by calling the `requestInterrupt` method, which is a delegate that's set by its controlling Dialogue Runner. When this method is called, all Dialogue Views that have not yet finished their presentation receive a call to their `InterruptLine` method.

`InterruptLine` is very similar to `RunLine`, in that it receives a line to present and a completion handler to call when the presentation is complete. However, while `RunLine` is expected to present the line at its own pace, `InterruptLine` is a signal to finish the presentation as quickly as possible.

As before, the actual details of this depend on the Line View. To continue the examples from before, a Dialogue View that plays voice-over audio might fade out the audio over a short period of time, or even cut off playback immediately; a Dialogue View that's gradually revealing text might reveal the remaining text all at once, or rapidly reveal the remaining text.

{% hint style="warning" %}
When a Dialogue View receives a call to `InterruptLine`, it should not call the completion handler that it received from the call to `RunLine`. Calls to interrupt a line supersede calls to run a line.
{% endhint %}

Any Dialogue View may request that a line be interrupted. If multiple Dialogue Views request it, only the first request does anything.

### Dismissing Lines

When the last Dialogue View reports that its presentation is complete, either because `RunLine` finished its presentation, or because `InterruptLine` was called and it quickly finished its presentation, it needs to tell the dialogue views to get rid of the line, and potentially prepare for more content.

The Dialogue Runner does this by calling `DismissLine` on all Dialogue Views. As with `RunLine` and `InterruptLine` before it, `DismissLine` receives a completion handler to call when it has finished dismissing the line.

As before, the details of how a line is dismissed vary with what the Dialogue View actually does. A Dialogue View that plays voice-over audio may not need to do anything to dismiss a line, because the playback has already finished; a Dialogue View that shows line text on screen might need to hide the text, possibly with an animation.

When the last Dialogue View reports that it has finished dismissing its line, the Dialogue Runner continues running the script.

### Presenting Options

Options are slightly different to lines, in that they rely on receiving some kind of user input before the dialogue can continue: the Dialogue Runner needs to know which option was selected.

To handle options, Dialogue Views implement the `RunOptions` method. This method receives an array of `DialogueOption` objects, each of which represents an option that can be shown to the user, as well as a completion handler.

When this method is called, the Dialogue View uses the information contained within the `DialogueOption` objects to present the choices to the player, and then awaits user input. Once it knows which option was selected, it calls the completion handler, passing in the `DialogueOptionID` of the selected option.

{% hint style="danger" %}
When the Dialogue Runner delivers options to its Dialogue Views, it expects exactly one of them to call the completion handler that `RunOptions` receives. 

* If _none_ of them call it, then the Dialogue Runner will never receive the option that was selected (and will wait for it forever.)
* If _more than one_ of them call it, the Dialogue Runner will throw an error.

(In most situations, you will generally only have one Dialogue View in your scene that handles options. If you have more than one, then you will need to control which one of them will call their completion handler.)
{% endhint %}

## Using Multiple Dialogue Views

Dialogue Runners can use multiple Dialogue Views. This is actually recommended, because it makes it easier to separate the code for handling lines, from that of running options.

All of the methods in `DialogueViewBase` are optional. If you don't implement a method, then the default implementation of that method is used instead; the default implementation either does nothing, or as close to nothing as it can while still working. For example, the default implementation of `RunLine` immediately signals that presentation is complete.

* To create a Dialogue View that shows lines, implement `RunLine`, `InterruptLine` and `DismissLine`.
* To create a Dialogue View that shows options, implement `RunOptions`.
* To create a Dialogue View that supports both, implement all four.

## Responding to Dialogue Advancement


During gameplay, your user may wish to indicate that they want to advance the dialogue: that is, they want to proceed to the next line, or they want the current line to be presented more quickly.

To handle this case, implementers of `DialogueViewBase` may implement the method `UserRequestedViewAdvancement`, which can be called by other parts of the game.

In most cases, it is generally appropriate for implementations of `UserRequestedViewAdvancement` to call the `requestInterrupt` method, which tells the Dialogue Runner to interrupt the line (across all views) and to proceed to the next one. However, a Dialogue View may choose to perform other actions that deliver the line more quickly.

{% hint style="info" %}
For example, in several text-based RPG games, dialogue is delivered as a text box, one letter at a time; when it's all delivered, the user can press the A button (to choose an arbitrary example) to proceed. 

If, however, you press the A button while the text is still appearing, all of the text appears all at once (as though we'd jumped ahead). 

Alternatively, if you pressed the B button while the text was still appearing, the line would be skipped, the dialogue would move to the next line.
{% endhint %}

`UserRequestedViewAdvancement` can be called by any part of your code.

## Accessing Line Metadata

To access the [tags](../../../getting-started/writing-in-yarn/tags-metadata.md) on a line, you use the `Metadata` property on the `LocalizedLine` objects you receive. It's up to your code to decide what to do with the tags themselves.

{% hint style="info" %}
Yarn Spinner will automatically add certain tags to lines. For example, the `#lastline` tag is automatically added to any line that's immediately followed by options, which allows your dialogue view to change its behaviour when options are about to appear.
{% endhint %}

## Modifying the Example Dialogue Systems

Two example scenes are provided with Yarn Spinner for Godot: `addons/YarnSpinner-Godot/Scenes/DefaultDialogueSystem.tscn` and `addons/YarnSpinner-Godot/Scenes/RoundedDialogueSystem.tscn`. 

Many projects ultimately end up needing to write their own custom dialogue view scripts to achieve the desired level of control over line and option presentation, but when first starting to integrate Yarn Spinner with your Godot game, it can be useful to start with the provided example views and modify their appearance and layout. These `.tscn` files provide a pre-configured LineView, DialogueRunner, and OptionsListView.  

To create your modified version, start by navigating to the `.tscn` file that you would like to base your views on in `addons/YarnSpinner-Godot/Scenes/`. In this example, we'll use the RoundedDialogueSystem.  Right click RoundedDialogueSystem.tscn and select the option "Move/Duplicate to...". Choose the directory in your project that you would like to save your dialogue system to, then click the 'Copy' button. 

{% hint style="warning" %}
Be careful not to select the 'Move' button on this step. If you do accidentally move the file instead of copying it, you can move it back by following the same process, selecting `addons/YarnSpinner-Godot/Scenes/` as the destination directory.
{% endhint %}

You now have a duplicate of the original `.tscn` file. You can rename it to anything you like. 
Double click your duplicated file to edit it.  

{% hint style="danger" %}
Before modifying any styles in your copy of the dialogue system, make sure to right click the StyleBox resource and select 'Make Unique' or 'Save As...'. If you select 'Save As...', chose a directory outside of the addons/ directory to save your modified style. If you don't do this step, any modifications that you make to the styles will be saved to the .tres files in Yarn Spinner for Godot's directory, meaning you will lose these changes the next time you update the plugin.  

Keep an eye on the addons/YarnSpinner-Godot directory as you customize your view using version control to ensure the .tres and .tscn files are not being modified.  
{% endhint %}

You can now edit the Controls in your new scene to arrange and style them to your liking. The Controls that your scene contains, such as Panels, RichTextLabels, VBoxContainers, and others, are built-in Godot UI components, so you use the same techniques that you would for any other Godot UI component to re-style them. One way to customize the appearance of your scene is by adding or modifying StyleBox resources on the various components (visible in the inspector for each node under Theme Overrides > Styles). You can also modify the anchor points of the Controls to change their position relative to the screen's edges and center.

It's recommended to become familiar with the fundamentals of working with Godot UI components before attempting to customize your dialogue system.