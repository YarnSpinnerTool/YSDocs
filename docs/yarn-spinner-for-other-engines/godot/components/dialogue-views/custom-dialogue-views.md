---
description: >-
  Learn how to create Dialogue Presenters that are designed for the specific
  needs of your game.
---

# Custom Dialogue Presenters

The Line Presenter and Options Presenter are handy for many situations. But your game might need to show lines and options in a particular way. When that's the case, you can write your own **custom Dialogue Presenter**. This gives you full control over how lines and options appear.

## **Creating a Dialogue Presenter**

To make a Dialogue Presenter, you write a script that implements the `DialogueViewBase` interface, and add your script to a node in your scene. You can then add this node to the Dialogue Views list in the inspector of your scene's Dialogue Runner.

### **Presenting Lines and Options**

By itself, an empty script implementing the `DialogueViewBase` interface will not do anything useful. To make it display lines and options, you'll need to implement certain methods.

To understand how to create a custom Dialogue View, it's useful to understand how the [Dialogue Runner](../dialogue-runner.md) works with content.

To get how custom Dialogue Presenters work, it helps to understand how the Dialogue Runner handles content. Yarn Spinner scripts use three types of content: **lines**, **options**, and **commands**. Only the first two, lines and options, need to be shown directly to the player.

When the Dialogue Runner finds lines or options, it first figures out the exact content the player needs to see. Once it has this, it sends the content to each of its Dialogue Presenters.

Your scene can have several Dialogue Presenters. And they can all do different things. For instance, you might have one Dialogue Presenter for lines, another for options, and a third for playing voice-over audio.


### **Getting Localised Content**

In compiled Yarn Spinner Scripts, Lines and Options are represented by line IDs. A line ID is a unique code for the text of a line or an option. When Yarn Spinner needs to show a line or option, it asks its Line Provider for a `LocalizedLine` object. This object holds the text for the line or option in the player's current language.

If you're showing a group of options, each option in that group has its own `LocalizedLine`.

Once a `LocalizedLine` is ready, the Dialogue Runner has everything it needs to show content. What happens next depends on whether it's showing a line or an option.

{% hint style="info" %}
For more information about setting up localization for your project using Yarn Spinner for Godot, see [here](../../localization.md)
{% endhint %}
 

### **Presenting Lines**

When Yarn Spinner comes across a line of dialogue, it calls the `RunLineAsync` method on every Dialogue Presenter. This method gets two things: first, the `LocalizedLine` from the Line Provider, and second, a `LineCancellationToken`. The Dialogue Presenter uses this token to know the line's status. Specifically, it checks if the player wants to speed up the line's display or move to the next line.

In Dialogue Presenters, a line is considered "presented" when the player has seen the whole line and is ready for the next one. What this means in practice varies. For example, a Dialogue Presenter playing voice-over audio might finish when all the audio has played. Another one that shows text gradually might finish when all text is visible and the UI has faded out.

The Dialogue Runner waits until all Dialogue Presenters say they've finished showing the line. Then, it moves to the next bit of dialogue.

The `RunLineAsync` method is asynchronous. This means a Dialogue Presenter signals it's done and ready for the next line by returning from the method.

If your game needs to pause dialogue until the player does something (like press a button), your Dialogue Presenter can do this. It simply doesn't return from the `RunLineAsync` method until the line cancellation token signals to advance. Because the Dialogue Runner waits for all presenters, the dialogue will pause until your presenter says to go on.

### **Hurrying and Advancing Lines**

Line presentation usually isn't instant. It typically happens over a short period. So, players might want to speed this up or skip it entirely. Dialogue Presenters need to be ready for the player to ask for a line to hurry up or be skipped at any moment during presentation.

The line's state is held in the `LineCancellationToken` given during the `RunLineAsync` method. This token wraps two other Cancellation Tokens: one for advancing to the next line, and one for making the current line hurry. These tokens are linked. So, if the "next line" token is flagged, the "hurry up" token will be too. But it doesn't work the other way around.

Most times, you won't need to access these tokens directly. You can check the line's status using handy properties. `IsHurryUpRequested` on the token tells your custom Dialogue Presenter if the player wants the display to go faster. And `IsNextLineRequested` tells you if your Dialogue Presenter should skip the current line completely.

Any part of line presentation that isn't instant should use these properties. This helps decide if they should speed up or be skipped. The same `LineCancellationToken` is shared by all Dialogue Presenters. So, if the line's status changes, all presenters see it at the same time. Each Dialogue Presenter decides what "hurrying up" means for it; it's a signal to finish the presentation quickly.

For example, a voice-over presenter might fade out audio quickly or cut it off. A text-revealing presenter might show all remaining text at once or very rapidly. Advancing a line is a more direct signal that the player wants the dialogue to move on. You shouldn't ignore `IsNextLineRequested` when it's true. Presenters should clean up and finish showing the line as soon as possible if the player has asked to advance.

{% hint style="info" %}
For some Dialogue Presenters, "hurry up" and "advance" might mean the same thing. Each presenter shows lines its own way. You decide how these signals work for your game.
{% endhint %}

You can change the `LineCancellationToken`'s state using the Dialogue Runner. It has two methods for this. `RequestHurryUpLine` sets the token so `IsHurryUpRequested` becomes true. `RequestNextLine` sets the `IsNextLineRequested` flag to true. Since the `LineCancellationToken` wraps two linked tokens, these methods also cancel those internal tokens. Requesting the next line also means requesting the line to hurry up. You can safely request a line advance or hurry up multiple times; it won't cause any issues.

{% hint style="info" %}
Don't cache the `LineCancellationToken` between lines. The Dialogue Runner creates new ones for each line. An old token won't be any use.
{% endhint %}

### **Presenting Options**

Options are a bit different from lines. They need some kind of player input before the dialogue can go on. The Dialogue Runner needs to know which option was picked.

To manage options, Dialogue Presenters implement the `RunOptionsAsync` method. This method gets an array of `DialogueOption` objects and a cancellation token. Each `DialogueOption` object is an option that can be shown to the player.

When this method is called, the Dialogue Presenter uses the info in the `DialogueOption` objects to show choices to the player. Then it waits for player input. Once it knows which option was selected, the method should return that chosen option. The Dialogue Runner then uses this to make the selection.

If your presenter doesn't need to handle options, it can return a null value instead.

{% hint style="info" %}
If `RunOptionsAsync` doesn't do any asynchronous tasks, it's neater to return `YarnTask<DialogueOption>.FromResult(null)`. This looks a bit less tidy than `return null;`, but it clearly tells C# that you're intentionally not doing any async work in the method.
{% endhint %}

The Dialogue Runner will ignore any nulls it gets back from presenters here. The first non-null `DialogueOption` it receives is treated as the selected one.

When the Dialogue Runner sends options to its Dialogue Presenters, it expects only one of them to return a non-null option. If none of them return an option, the Dialogue Runner will never know what was picked. And it will wait forever, and ever, and ever.

If more than one presenter returns an option, the Dialogue Runner uses the first one it gets and ignores the others. After getting a non-null option, the Dialogue Runner cancels the cancellation token given in the method. This tells any presenters that haven't returned yet that an option has been selected. So, they can stop waiting for a selection.


### **Accessing Line Metadata**

To get the tags on a line, you use the `Metadata` property on the `LocalizedLine` objects you receive. Your code decides what to do with these tags.

{% hint style="info" %}
Yarn Spinner automatically adds certain tags to lines. The `#lastline` tag is added to any line that's immediately followed by options. This lets your dialogue presenter change how it behaves when options are about to appear.
{% endhint %}

### Modifying the Example Dialogue Systems

Two example scenes are provided with Yarn Spinner for Godot: `addons/YarnSpinner-Godot/Scenes/DefaultDialogueSystem.tscn` and `addons/YarnSpinner-Godot/Scenes/RoundedDialogueSystem.tscn`.

Many projects ultimately end up needing to write their own custom Dialogue Presenter scripts to achieve the desired level of control over line and option presentation, but when first starting to integrate Yarn Spinner with your Godot game, it can be useful to start with the provided example presenters and modify their appearance and layout. These `.tscn` files provide a pre-configured Line Presenter, DialogueRunner, and Options Presenter.

To create your modified version, start by navigating to the `.tscn` file that you would like to base your views on in `addons/YarnSpinner-Godot/Scenes/`. In this example, we'll use the RoundedDialogueSystem. Right click RoundedDialogueSystem.tscn and select the option "Move/Duplicate to...". Choose the directory in your project that you would like to save your dialogue system to, then click the 'Copy' button.

{% hint style="warning" %}
Be careful not to select the 'Move' button on this step. If you do accidentally move the file instead of copying it, you can move it back by following the same process, selecting `addons/YarnSpinner-Godot/Scenes/` as the destination directory.
{% endhint %}

You now have a duplicate of the original `.tscn` file. You can rename it to anything you like. Double click your duplicated file to edit it.

{% hint style="danger" %}
Before modifying any styles in your copy of the dialogue system, make sure to right click the StyleBox resource and select 'Make Unique' or 'Save As...'. If you select 'Save As...', chose a directory outside of the addons/ directory to save your modified style. If you don't do this step, any modifications that you make to the styles will be saved to the .tres files in Yarn Spinner for Godot's directory, meaning you will lose these changes the next time you update the plugin.

Keep an eye on the addons/YarnSpinner-Godot directory as you customize your presenters using version control to ensure the .tres and .tscn files are not being modified.
{% endhint %}

You can now edit the Controls in your new scene to arrange and style them to your liking. The Controls that your scene contains, such as Panels, RichTextLabels, VBoxContainers, and others, are built-in Godot UI components, so you use the same techniques that you would for any other Godot UI component to re-style them. 

One way to customize the appearance of your scene is by adding or modifying StyleBox resources on the various components (visible in the inspector for each node under Theme Overrides > Styles). You can also modify the anchor points of the Controls to change their position relative to the screen's edges and center.

It's recommended to become familiar with the fundamentals of working with Godot UI components before attempting to customize your dialogue system.
