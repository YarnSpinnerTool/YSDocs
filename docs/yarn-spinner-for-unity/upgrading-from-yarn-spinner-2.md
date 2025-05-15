---
description: >-
  Learn about updating a Unity project to use Yarn Spinner 3 when it's already
  using Yarn Spinner 2.
icon: conveyor-belt-boxes
---

# Upgrading from Yarn Spinner 2

Yarn Spinner 3 introduces mostly additive changes to the language. However, Yarn Spinner for Unity has had a number of breaking changes to support these new features.

When migrating a game from v2 to v3, we provide compatibility layers to handle many changes automatically. Still, some minor adjustments will be necessary. This guide covers the essential steps to make existing Yarn Spinner v2 games compatible with v3. It also outlines how to replace older systems with the new ones.

#### Compatibility Presenter

Yarn Spinner v3 moves from the complex, callback-based `DialogueViewBase` to a simpler, asynchronous `DialoguePresenter`. This is now the primary way your code receives dialogue events.

Presenters and views share similarities, but presenters have a different API and are incompatible with older views. We strongly recommend refactoring your old views to the new presenter model.

If you wish to continue using an existing dialogue view, the `DialogueViewBase` class has been modified. It now functions as a compatibility version of the new presenters. Consequently, the namespace for `DialogueViewBase` has changed to reflect its intended use. For your older dialogue views to function, you must include the `Yarn.Unity.Legacy` namespace.

#### YarnCommand and YarnFunction Attributes

The behaviour of the `[YarnCommand]` and `[YarnFunction]` attributes remains unchanged. However, due to a namespacing issue, they have been moved. To access these attributes, include the `Yarn.Unity.Attributes` namespace in any C# files that use them.

#### Interrupting Dialogue

The method for hurrying, advancing, and cancelling dialogue has been completely redesigned.

When presenters receive dialogue events (like showing options or a line), they are given a cancellation token. You can read the state of this token at any time. This determines if something has requested the current line to be advanced. This change allows all presentation, cancellation, and clean-up code to reside in one place, rather than being split across multiple methods.

The `Line Advancer` sample demonstrates one way to handle line advancement using this new cancellation token-based approach.

#### Converting a Dialogue View into a Dialogue Presenter

Although the `DialoguePresenter` and `DialogueView` APIs may seem similar, they operate quite differently.

Previously, views coordinated with the dialogue runner by internally managing a callback provided by the runner. `DialoguePresenter`s use asynchronous functions. They signal completion by returning from the method. This significantly simplifies operations for both the dialogue runner and your custom presenters.

The process for converting a view to a presenter will vary based on your view's functionality. However, the general steps are:

1. **Change the subclass.**
2. **Convert to the new methods.**
3. **Delete unnecessary methods.**
4. **Remove the Interrupt action.**

**1. Change the Subclass**

First, replace `DialogueViewBase` with `DialoguePresenterBase` as the subclass. Since `DialogueViewBase` is itself a subclass of `DialoguePresenterBase`, this change should not break the connection to the dialogue runner in Unity. However, always verify that it is correctly hooked up after completing the conversion.

**2. Convert to the New Methods**

While presenter methods do not have a one-to-one correspondence with view methods, they share some common ground. The following methods relate to the same dialogue events in both systems:

| **Old View Method** | **New Presenter Method**  |
| ------------------- | ------------------------- |
| `DialogueStarted`   | `OnDialogueStartedAsync`  |
| `RunLine`           | `RunLineAsync`            |
| `RunOptions`        | `RunOptionsAsync`         |
| `DialogueComplete`  | `OnDialogueCompleteAsync` |

**3. Delete Unnecessary Methods**

The old dialogue view used callbacks and specific methods to handle user interruption and line completion. This functionality is now managed by cancellation tokens within the presenter.

Therefore, the following methods can be deleted:

* `InterruptLine`
* `DismissLine`
* `UserRequestedViewAdvancement`

**4. Remove the Interrupt Action**

Finally, the `requestInterrupt` action can be deleted as it no longer serves any purpose.

**Final Steps**

The remaining work involves replicating your view's original behaviour in the new presenter. We provide several samples showcasing various custom dialogue presenters. These examples can help you understand how to implement this.
