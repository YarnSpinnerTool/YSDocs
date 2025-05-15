---
icon: conveyor-belt-boxes
---

# Upgrading from Yarn Spinner 2

While Yarn Spinner v3 is a mostly additive change to the language itself there have been breaking changes made to the Unity integration to support these new features.
When migrating a game from v2 to v3 we have provided compatibility layers which handle things for you, there will still need to be some small tweaks and changes.
This doc covers the necessary elements to make existing Yarn Spinner v2 games work with v3 as well as the steps to fully replace the older systems with newer ones.

## Compatibility Presenter

In Yarn Spinner v3 we have moved away from the complex callback based `DialogueViewBase` to a newer and simpler async `DialoguePresenter` as the main way for your code to receive important dialogue events.
While there are similarities between presenters and views the presenters do have a different API to the older views and are incompatible with them.
We highly suggest refactoring your older views into the newer presenter model.

If you have an existing dialogue view that you want to keep using we have modified the previous `DialogueViewBase` class to be a compatibility form of the newer presenters.
As part of this the namespace of the dialogue view base has changed to more clearly indicate its intended use.
From a practical perspective this means you need to include the `Yarn.Unity.Legacy` namespace for your older dialogue views to continue to work.

## Yarn Command and Function attributes

While the behaviour of the `[yarncommand]` and `[yarnfunction]` attributes haven't changed, due to some namespacing issue these have been moved into a different namespace.
To get access to these attributes again include the attributes namespace `using Yarn.Unity.Attributes;` in any C# files that use the Yarn Command and Function attributes.

## Interrupting Dialogue

The previous way of hurrying, advancing, and cancelling dialogue has been completely changed.
When presenters are told about important dialogue events, such as it being time to show options or a line, it is given a cancellation token.
The state of this token can be read at any time and used to determine if something has requested that the current line be advanced.

This allows for all presentation, cancellation, and clean up code to all live in the same place now instead of being split up over multiple.
The Line Advancer demonstrates one approach to handling line advancement using this new approach based around cancellation tokens.

## Converting a Dialogue View into a Dialogue Presenter

While a lot of the Dialogue Presenter vs Dialogue View APIs look very similar they work in quite a different fashion.
In the past the way views coordinated with the dialogue runner was through internally managing a callback given to them by the dialogue runner.
Dialogue Presenters use async functions so the way they signal their completion is by returning from the method.
This massively simplifies things for both the dialogue runner and for your own custom presenters.

The process for porting a view into a presenter will change greatly depending on what your view does, but in general it's as follows:

1. Change the subclass
2. Convert to the new methods
3. Delete the unnecessary methods
4. Remove the Interrupt action

### Change the subclass

The first step is to replace the `DialogueViewBase` subclass with `DialoguePresenterBase`.
Because the dialogue view base is itself a subclass of dialogue presenter base this *shouldn't* have broken the connection in Unity to the dialogue runner, but it is always worth checking that this is still correctly hooked up after finishing the conversion.

### Convert to the new methods

While the presenter methods aren't one to one to the view methods they share some commonality.
In particular the following methods relate to the same dialogue event in both:

| Dialogue Presenter      | Dialogue View    |
|-------------------------|------------------|
| OnDialogueStartedAsync  | DialogueStarted  |
| RunLineAsync            | RunLine          |
| RunOptionsAsync         | RunOptions       |
| OnDialogueCompleteAsync | DialogueComplete |

### Delete the unnecessary methods

The dialogue view uses callbacks and methods to handle user interruption and line completion, this is now encapsulated in cancellation tokens in the presenter.
This means the following methods can be deleted:

- InterruptLine
- DismissLine
- UserRequestedViewAdvancement

### Remove the Interrupt action

Finally the `requestInterrupt` action can be deleted, it no longer serves any purpose.

### Draw the rest of the owl

At this point the rest of the work is in recreating the same behaviour in your presenter that your view used to have.
We have several samples which show off a variety of custom dialogue presenters to help get a grasp on doing exactly this.
