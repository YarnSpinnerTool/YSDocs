---
description: >-
  Learn about updating a Unity project to use Yarn Spinner 3 when it's already
  using Yarn Spinner 2.
icon: conveyor-belt-boxes
---

# Upgrading from Yarn Spinner 2

**Yarn Spinner 3** introduces primarily additive changes to its language. Significant modifications have been made to **Yarn Spinner for Unity** to support these new features, resulting in some breaking changes.

{% hint style="danger" %}
You only need to refer to this page if you've got a project that's already being developed in Yarn Spinner for Unity 2, and you want to transition to Yarn Spinner for Unity 3. If you're starting a new Unity project and plan to work with Yarn Spinner, you should be using Yarn Spinner 3.
{% endhint %}

This guide assists in migrating Yarn Spinner for Unity 2 projects to Yarn Spinner 3. While we provide compatibility layers to automatically manage many of the changes, some manual adjustments will be necessary. Here we'll look at the steps to ensure existing Yarn Spinner 2 games function with Yarn Spinner for Unity 3, and outline how to transition to the newer systems.

## YarnCommand and YarnFunction Attributes

The functionality of `[YarnCommand]` and `[YarnFunction]` attributes is unchanged. However, they have been moved to a new namespace. To use these attributes, add `using Yarn.Unity.Attributes;` to the relevant C# files.

## New flow for Interrupting Dialogue

The system for managing dialogue interruption (hurrying, advancing, cancelling) has been redesigned.

When Presenters receive dialogue events, such as requests to show lines or options, they are provided with a cancellation token. The state of this token can be checked to determine if an advance has been requested. This design centralises presentation, cancellation, and cleanup logic, which was previously distributed across multiple methods.

## DialogueViewBase is now DialoguePresenter

Yarn Spinner 3 replaces the callback-based `DialogueViewBase` with an asynchronous `DialoguePresenter`. This is the new standard for handling dialogue events in your code.

While Presenters and Views have functional similarities, Presenters utilize a different API and are not directly compatible with older Views. If you're migrating from Yarn Spinner 2.0, you'll need to update your older Dialogue View classes to be Dialogue Presenters.

### Converting a Dialogue View to a Dialogue Presenter

Previously, **Dialogue Views** used callbacks to coordinate with the dialogue runner. **Dialogue Presenters** employ asynchronous functions, signalling completion by returning from the method. This simplifies logic for both the dialogue runner and custom Dialogue Presenter implementations.

While the APIs of the old Dialogue View and the new Dialogue Presenter may appear similar, their operational mechanics differ significantly.

The conversion process will vary depending on the specific functionality of your View, but the general steps are:

1. **Change the Subclass.**
2. **Convert to the New Methods.**
3. **Delete Unnecessary Methods.**
4. **Remove the Interrupt Action.**

### **1. Change the Subclass**

Replace `DialogueViewBase` with `DialoguePresenterBase` as the base class. 

### **2. Convert to the New Methods**

While not a direct one-to-one mapping, several Presenter methods correspond to View methods in terms of the dialogue events they handle:

| **Old DialogueViewBase Method** | **New DialoguePresenterBase Method** |
| ------------------------------- | ------------------------------------ |
| `DialogueStarted`               | `OnDialogueStartedAsync`             |
| `RunLine`                       | `RunLineAsync`                       |
| `RunOptions`                    | `RunOptionsAsync`                    |
| `DialogueComplete`              | `OnDialogueCompleteAsync`            |

### **3. Delete Unnecessary Methods**

The old `DialogueView` used callbacks and specific methods for user interruption and line completion. This functionality is now handled by cancellation tokens within the Presenter.

The following methods are no longer needed and can be removed:

* `InterruptLine`
* `DismissLine`
* `UserRequestedViewAdvancement`

### **4. Remove the Interrupt Action**

The `requestInterrupt` action is obsolete and can be deleted.

### **Final Steps**

The remaining task is to replicate the original behaviour of your Dialogue View within the new Dialogue Presenter structure. Several [samples](../yarn-spinner-for-unity/samples/ "mention") are available, showcasing various custom Dialogue Presenters, which can provide guidance and practical examples for this process.

## Upgrading Yarn Projects

Any new Yarn Projects you create will be already configured correctly but if you have any existing v2 Yarn Projects these will need to be updated.\
This is a single change that needs to be done on each Yarn Project.\
If you open your Yarn Projects inside any text editor there will be a line inside that says `"projectFileVersion": 2,`, replace this with `"projectFileVersion": 3,` and save the file.\
When you go back to Unity this change will be detected and the project will be automatically reimported at which stage you can now use v3 features in that project.
