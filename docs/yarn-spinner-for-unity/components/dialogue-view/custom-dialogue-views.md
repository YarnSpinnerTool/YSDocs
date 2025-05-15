---
description: >-
  Learn how to create Dialogue Presenters that are designed for the specific
  needs of your game.
---

# Custom Dialogue Presenters

While the Line Presenter and Options Presenter are useful for lots of situations, your game might need to display lines and options in specific ways. In these situations, you can write your own custom Dialogue Presenter, and handle the presentation of lines and options in ways that are entirely in your control.

### Creating a Dialogue Presenter

To create a Dialogue Presenter, you subclass the `DialoguePresenterBase` class, and add it as a component to a game object in your scene. You can then add this game object to the Dialogue Presenters list on your scene's Dialogue Runner.

### Presenting Lines and Options

On its own, an empty subclass of `DialoguePresenterBase` will not do anything useful. To make it display lines and options, you'll need to implement certain methods.

To understand how to create a custom Dialogue Presenter, it's useful to understand how the [Dialogue Runner](../dialogue-runner.md) works with content.

Yarn Spinner scripts deal in three different kinds of content: lines, options, and commands. Of these, only the first two - lines and options - are content that need to be shown directly to the player.

When the Dialogue Runner encounters lines or options, it first needs to determine the specific content the user needs to see. Once it has this, it sends the content to each of its Dialogue Presenter.

{% hint style="info" %}
Your scene can have multiple Dialogue Presenters, and they can all do different things. It can be useful to create, for example, a Dialogue Presenter that handles lines, another that handles options, and one more to handle playback of voice over audio.
{% endhint %}

#### Getting Localized Content

Lines and options are represented in compiled Yarn scripts as _line IDs_. A line ID is a unique identifier for the text of a line or an option. When Yarn Spinner needs to show a line or option to the user, it asks its [Line Provider](../line-provider/) to provide it with a [`LocalizedLine`](broken-reference/) object. This object contains the text of the line or option, in the user's current locale.

{% hint style="info" %}
When displaying a group of options, each individual option in the collection has its own `LocalizedLine`.
{% endhint %}

Once a `LocalizedLine` has been created, the Dialogue Runner has everything that it needs to show content to the user. The next steps vary depending on whether it's showing a line or an option.

#### Presenting Lines

When Yarn Spinner encounters a line of dialogue, it calls the [`RunLineAsync`](link/) method on each Dialogue Presenter.\
This method takes two parameters: the first is the `LocalizedLine` that the Line Provider created, and the second is a [`LineCancellationToken`](link/) that the Dialogue Presenter can use to know about the state of line, in particular if the player wants the line to hurry up it's presentation or to advance to the next line.

In Dialogue Presenters, a line is _presented_ when the player has received the entire line, and is ready to move on to the next line. The practical outcome of what this means depends on the Dialogue Presenter itself; for example, a Dialogue Presenter that plays voice-over audio might finish presenting when all of the audio has played, while a Dialogue Presenter that gradually reveals the text of a line might finish presenting when all of the text is visible and the UI itself has then faded to transparent.

The Dialogue Runner will wait until all Dialogue Presenters report that they've finished presenting the line. Once this happens, it moves on to the next part of the dialogue.\
As the method is asynchronous this means a Presenter indicates it has finished presentation and is ready for the next line by returning.

{% hint style="info" %}
If you're making a game where you want the dialogue to pause until the user gives a signal to proceed (such as needing them to press a button to continue), your Dialogue Presenter can pause the dialogue by not returning from the method until the line cancellation token is flagged as needing to advance to the next line. Because the Dialogue Runner will wait until _all_ Dialogue Presenters report that they're done, the dialogue will wait until your presenter tells it to continue.
{% endhint %}

#### Hurrying and Advancing Lines

Line presentation is rarely instaneous, it will happen over a period of time.\
This means the players may well want to have that period of time reduced, or skipped entirely.\
Dialogue Presenters should be prepared for the player to request a line hurry up, or be skipped entirely, at any time during presentation.

The state of the line is encapsulated inside of the Line Cancellation Token it was given as part of the RunLineAsync method.\
This is a wrapper around two [Cancellation Tokens](https://learn.microsoft.com/en-us/dotnet/api/system.threading.cancellationtoken) one for signalling to advance to the next line and one that the current line should hurry up.\
These tokens are linked in a hierarchy, so if the next line token has been flagged as needing advancement then so too will the hurry up token, but not the other way around.

Most of the time you won't need to directly access the tokens, although you can if you wish, you can check the status of the line via convenience properties.`IsHurryUpRequested` on the token lets your custom presenter know if the player wants the presentation to go faster, and `IsNextLineRequested` lets you know if the presenter should skip over this line entirely.\
Any element of line presentation that will be non-instanteous should use these properties to determine if they should hurry up or be skipped.\
As the same Line Cancellation Token is shared by all Dialogue Presenters if the status of the line has changed this is reflected to all Presenters simultaneously.

It is up to each Dialogue Presenter to handle what hurrying up a line means for them, it is a signal to finish the presentation.\
To continue the examples from before, a Dialogue Presenter that plays voice-over audio might fade out the audio over a short period of time, or even cut off playback immediately; a Dialogue Presenter that's gradually revealing text might reveal the remaining text all at once, or rapidly reveal the remaining text.

When it comes to advancing a line this is a more direct signal that the user wants the dialogue to continue.\
Ignoring when `IsNextLineRequested` is set to true is not recommended, presenters should clean up and finish presentation as soon as possible when the player has asked the line to advance.

{% hint style="info" %}
For some presenters being told to hurry up and advance mean the same thing.\
Each presenter has it's own way of presenting a line, it's up to you to handle what these signals means for you and your game.
{% endhint %}

The way you can change the state of the Line Cancellation Token is via the Dialogue Runner.\
It has two methods for this, `RequestHurryUpLine` will set the token such that `IsHurryUpRequested` is true, and `RequestNextLine` will set the `IsNextLineRequested` flag to true.\
As the Line Cancellation Token is a wrapper around two linked cancellation tokens these methods will also cancel these internal tokens, and requesting the next line is the same as also requesting the line hurry up.\
It is safe to request a line advance or hurry up as many times as you want, it won't impact anything to do so.

{% hint style="danger" %}
Do not cache the Line Cancellation Token between lines.\
The Dialogue Runner will make new ones for each line, an old token is of no use to you.
{% endhint %}

#### Presenting Options

Options are slightly different to lines, in that they rely on receiving some kind of user input before the dialogue can continue: the Dialogue Runner needs to know which option was selected.

To handle options, Dialogue Presenters implement the [RunOptionsAsync](link/) method.\
This method receives an array of [DialogueOption](broken-reference/) objects, each of which represents an option that can be shown to the user, as well as a cancellation token.

When this method is called, the Dialogue Presenter uses the information contained within the `DialogueOption` objects to present the choices to the player, and then awaits user input.\
Once it knows which option was selected the method should return the selected option, this is then used by the Dialogue Runner to make the selection.\
If your presenter doesn't need to handle options it can instead return a null value.

{% hint style="info" %}
If you don't perform any asynchronous events in `RunOptionsAsync` it is cleaner to instead `return YarnTask<DialogueOption>.FromResult(null);` which is less nice looking than `return null;` it does make it clear to C# that you are intentionally not doing any async work in the method.
{% endhint %}

The Dialogue Runner will ignore any nulls it gets back from presenters here.\
The first non-null Dialogue Option it gets back is the selected one.\
When the Dialogue Runner delivers options to its Dialogue Presenters, it expects only one of them to return a non-null option.

* If _none_ of them return, then the Dialogue Runner will never receive the option that was selected (and will wait for it forever.)
* If _more than one_ of them call it, the Dialogue Runner will use the first and ignore any other.

After getting back a non-null option the Dialogue Runner will cancel the cancellation token provided in the method, this lets any Presenters that haven't returned yet know an option has been selected and they can stop waiting for a selection.

### Accessing Line Metadata

To access the [tags](../../../write-yarn-scripts/editing-with-vs-code/tags-metadata.md) on a line, you use the [Metadata](broken-reference/) property on the [LocalizedLine](broken-reference/) objects you receive. It's up to your code to decide what to do with the tags themselves.

{% hint style="info" %}
Yarn Spinner will automatically add certain tags to lines. For example, the `#lastline` tag is automatically added to any line that's immediately followed by options, which allows your dialogue presenter to change its behaviour when options are about to appear.
{% endhint %}
