# DialogueAdvanceInput

Class in [Yarn.Unity](../)

Inherits from `UnityEngine.MonoBehaviour`

## Summary

A component that listens for user input, and uses it to notify a dialogue view that the user wishes to advance to the next step in the dialogue.

```csharp
public class DialogueAdvanceInput : MonoBehaviour
```

## Remarks

This class may be used with the Unity Input System, or the legacy Input Manager. The specific type of input it's looking for is configured via the [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) field.

When the configured input occurs, this component calls the [UserRequestedViewAdvancement()](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.userrequestedviewadvancement.md) method on its [dialogueView](yarn.unity.dialogueadvanceinput.dialogueview.md).

## Enums

| Name                                                                        | Description                                                                                                      |
| --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| [ContinueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-1/) | The type of input that this component is listening for in order to signal that its dialogue view should advance. |

## Fields

| Name                                                                                  | Description                                                                                                                                                                                           |
| ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [continueAction](yarn.unity.dialogueadvanceinput.continueaction.md)                   | The `UnityEngine.InputSystem.InputAction` that this component is listening for.                                                                                                                       |
| [continueActionKeyCode](yarn.unity.dialogueadvanceinput.continueactionkeycode.md)     | The keyboard key that this component is listening for.                                                                                                                                                |
| [continueActionReference](yarn.unity.dialogueadvanceinput.continueactionreference.md) | An `UnityEngine.InputSystem.InputActionReference` that refers to the action that this component is listening for.                                                                                     |
| [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md)         | The type of input that this component is listening for.                                                                                                                                               |
| [dialogueView](yarn.unity.dialogueadvanceinput.dialogueview.md)                       | The dialogue view that will be notified when the user performs the advance input (as configured by [continueActionType](yarn.unity.dialogueadvanceinput.continueactiontype-2.md) and related fields.) |
| [enableActionOnStart](yarn.unity.dialogueadvanceinput.enableactiononstart.md)         | Configures whether [Action](yarn.unity.dialogueadvanceinput.action.md) should be enabled on start.                                                                                                    |

## Properties

| Name                                                | Description                                                                                    |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [Action](yarn.unity.dialogueadvanceinput.action.md) | Gets the `UnityEngine.InputSystem.InputAction` configured by this [DialogueAdvanceInput](./) . |
