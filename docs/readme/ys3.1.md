# Yarn Spinner 3.1

Yarn Spinner for Unity 3.1 contains a number of improvements and useful changes.

## Dialogue Runner Is Now More Async

The dialogue runner's `StartDialogue` and `Stop` methods are now `async`, and return a task. When you call `StartDialogue`, you'll receive a task (either a `System.Threading.Tasks` task, a `UnityEngine.Awaitable`, or a `UniTask`) that will complete after every dialogue presenter has finished running its `OnDialogueStartedAsync` method. Likewise, the `Stop` method will finish after every dialogue presenter has finished running its `OnDialogueCompleteAsync` method. This is really useful for making sure that you don't accidentally make a change to your scene in the middle of your dialogue presenters getting ready.

## Dialogue Option Fallthrough

In Yarn Spinner, you can add a condition to the end of an option. If the condition evaluates to `false`, Yarn Spinner will mark the option as "unavailable". It's up to your game to decide what that means - you might want to make the option visible but unselectable, or you might want to hide the option from the player entirely. However, if _every_ option is unavailable, the player has no option they could select. Previously, this could cause your game to have to soft-lock the player, since they weren't able to proceed.

In Yarn Spinner 3.1, dialogue presenters are now allowed to tell the Dialogue Runner that no option was selected at all. When this happens, Yarn Spinner will skip the options and move on to the next part of the script:

```
Guard: Who goes there?

// If the player is a thief, a royal visitor, or a merchant, then
// go run the appropriate conversation for that. The player might be
// some combination of the three, so let them choose.
-> A thief! <<if $player_is_thief>>
    <<jump Guard_Thief_Conversation>>
-> A royal visitor! <<if $player_is_royal_visitor>>
    <<jump Guard_RoyalVisitor_Conversation>>
-> A merchant! <<if $player_is_merchant>>
    <<jump Guard_Merchant_Conversation>>

// But if the player is NONE of those, then none of the options would have
// been available. We'll fall through to here.

Player: I'm nobody!
<<jump Guard_Nobody_Conversation>>
```

{% hint style="info" %}
You can turn off this behaviour by setting the `allowOptionFallthrough` property on your `DialogueRunner` to `false`.
{% endhint %}

## Lines Know Where They Came From

When Yarn Spinner sends a line to your game, it wraps up the line in an object called a [`LocalizedLine`](/docs/api/csharp/yarn.unity.localizedline.md). Previously, if your game has multiple Dialogue Runners that are running at the same time, it wasn't possible to know which runner the line came from. In Yarn Spinner 3.1, the `LocalizedLine` now has a [`Source`](/docs/api/csharp/yarn.unity.localizedline.source.md) property that tells you where it came from.

## Options Can Now Be Hurried Up And Cancelled

Just like how lines have a separate 'hurry up' and 'next' cancellation tokens that act as a signal to move things along, options now have the same 'hurry up' and 'next' tokens. (Previously, they only had a single cancellation token that signalled that option selection was no longer necessary.) This allows your game to signal that you want to hurry up the presentation of your dialogue's options.

## New Typewriter System

We've updated the way that typewriters are used in the built-in Line Presenter system, to make it easier to customise. This is useful for when you want to take full control over how the line appears over time, and for when you want to have in-game events occur (like sound effects) as the line appears.

To create a custom typewriter, create a class that implements [`IAsyncTypewriter`](/docs/api/csharp/yarn.unity.iasynctypewriter.md). You can find an example of how to write a custom typewriter in the source code for the [`LetterTypewriter`](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/Views/Typewriter/LetterTypewriter.cs) class.

{% hint style="info" %}
As part of this change, the On Character Typed event on Line Presenter has been removed. If you want to run code every time a character appears, create a new script that subclasses from [ActionMarkupHandler](/docs/api/csharp/yarn.unity.actionmarkuphandler.md), and add that to an object in your scene. Add that object to the Line Presenter's "Event Handlers" list. In your ActionMarkupHandler subclass, you can write code that gets called every time characters appear on screen by implementing the [OnCharacterWillAppear method](/docs/api/csharp/yarn.unity.iactionmarkuphandler.oncharacterwillappear.md).
{% endhint %}

## Removed Legacy `DialogueView` Classes

Yarn Spinner 3.0 introduced a new programming model for presenting dialogue, called [Dialogue Presenters](/docs/yarn-spinner-for-unity/components/dialogue-view/README.md). As part of the rollout of this new API, we made the old `DialogueView` class act as a compatibility layer, and marked it as deprecated. Yarn Spinner 3.1 removes this deprecated code. If you have code that started life as a Yarn Spinner 2.0 project, you will need to [migrate your legacy dialogue presentation UI code to use Dialogue Presenters](/docs/changelog/upgrading-from-yarn-spinner-2.md#converting-a-dialogue-view-to-a-dialogue-presenter).