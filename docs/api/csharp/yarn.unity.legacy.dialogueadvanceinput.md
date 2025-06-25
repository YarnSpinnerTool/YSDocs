# DialogueAdvanceInput

Class in [Yarn.Unity.Legacy](yarn.unity.legacy.md)

Inherits from `UnityEngine.MonoBehaviour`

{% hint style="warning" %}
This class is obsolete and may be removed from a future version of Yarn Spinner.
{% endhint %}

## Summary

A component that listens for user input, and uses it to notify a\
dialogue view that the user wishes to advance to the next step in the\
dialogue.

```csharp
public class DialogueAdvanceInput : MonoBehaviour
```

## Remarks

This class may be used with the Unity Input System, or the legacy\
Input Manager. The specific type of input it's looking for is configured\
via the [continueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md) field.

When the configured input occurs, this component calls the [UserRequestedViewAdvancement()](yarn.unity.legacy.dialogueviewbase.userrequestedviewadvancement.md) method on its[dialogueView](yarn.unity.legacy.dialogueadvanceinput.dialogueview.md).

## Enums

| Name                                                                                           | Description                                                                                                      |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| [ContinueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-1.md)           | The type of input that this component is listening for in order to signal that its dialogue view should advance. |
| [ContinueButtonActionType](yarn.unity.legacy.dialogueadvanceinput.continuebuttonactiontype.md) | The button/keycode action type, should the button be fired on release or press?                                  |

## Fields

| Name                                                                                                     | Description                                                                                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [continueAction](yarn.unity.legacy.dialogueadvanceinput.continueaction.md)                               | The `UnityEngine.InputSystem.InputAction` that this component is listening for.                                                                                                                              |
| [continueActionButtonName](yarn.unity.legacy.dialogueadvanceinput.continueactionbuttonname.md)           | The virtual button that this component is listening for.                                                                                                                                                     |
| [continueActionKeyCode](yarn.unity.legacy.dialogueadvanceinput.continueactionkeycode.md)                 | The keyboard key that this component is listening for.                                                                                                                                                       |
| [continueActionOnButtonRelease](yarn.unity.legacy.dialogueadvanceinput.continueactiononbuttonrelease.md) | Should the continue action respond to key being pressed down or released.                                                                                                                                    |
| [continueActionReference](yarn.unity.legacy.dialogueadvanceinput.continueactionreference.md)             | An `UnityEngine.InputSystem.InputActionReference` that refers to the action that this component is listening for.                                                                                            |
| [continueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md)                     | The type of input that this component is listening for.                                                                                                                                                      |
| [dialogueView](yarn.unity.legacy.dialogueadvanceinput.dialogueview.md)                                   | The dialogue view that will be notified when the user performs the advance input (as configured by [continueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md) and related fields.) |
| [enableActionOnStart](yarn.unity.legacy.dialogueadvanceinput.enableactiononstart.md)                     | Configures whether [Action](yarn.unity.legacy.dialogueadvanceinput.action.md) should be enabled on start.                                                                                                    |

## Properties

| Name                                                       | Description                                                                                                                           |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| [Action](yarn.unity.legacy.dialogueadvanceinput.action.md) | Gets the `UnityEngine.InputSystem.InputAction` configured by this [DialogueAdvanceInput](yarn.unity.legacy.dialogueadvanceinput.md) . |
