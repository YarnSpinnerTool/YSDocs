# DialogueAdvanceInput

Class in [Yarn.Unity.Legacy](/docs/api/csharp/yarn.unity.legacy.md)

Inherits from `UnityEngine.MonoBehaviour`

{% hint style="warning" %}
This class is <b>obsolete</b> and may be removed from a future version of Yarn Spinner.
{% endhint %}

## Summary


A component that listens for user input, and uses it to notify a
dialogue view that the user wishes to advance to the next step in the
dialogue.


```csharp
public class DialogueAdvanceInput : MonoBehaviour
```

## Remarks

<p>This class may be used with the Unity Input System, or the legacy
Input Manager. The specific type of input it's looking for is configured
via the [UserRequestedViewAdvancement()](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> field.</p> <p>When the configured input occurs, this component calls the <a href="yarn.unity.legacy.dialogueviewbase.userrequestedviewadvancement.md) method on its
[dialogueView](yarn.unity.legacy.dialogueadvanceinput.dialogueview.md).
</p>

## Enums

|Name|Description|
|:---|:---|
|[ContinueActionType](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactiontype-1.md)|The type of input that this component is listening for in order to signal that its dialogue view should advance.|
|[ContinueButtonActionType](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continuebuttonactiontype.md)|The button/keycode action type, should the button be fired on release or press?|

## Fields

|Name|Description|
|:---|:---|
|[continueAction](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueaction.md)|The  `UnityEngine.InputSystem.InputAction`  that this component is listening for.|
|[continueActionButtonName](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactionbuttonname.md)|The virtual button that this component is listening for.|
|[continueActionKeyCode](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactionkeycode.md)|The keyboard key that this component is listening for.|
|[continueActionOnButtonRelease](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactiononbuttonrelease.md)|Should the continue action respond to key being pressed down or released.|
|[continueActionReference](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactionreference.md)|An  `UnityEngine.InputSystem.InputActionReference`  that refers to the action that this component is listening for.|
|[continueActionType](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md)|The type of input that this component is listening for.|
|[dialogueView](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.dialogueview.md)|The dialogue view that will be notified when the user performs the advance input (as configured by  [continueActionType](yarn.unity.legacy.dialogueadvanceinput.continueactiontype-2.md)  and related fields.)|
|[enableActionOnStart](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.enableactiononstart.md)|Configures whether  [Action](yarn.unity.legacy.dialogueadvanceinput.action.md)  should be enabled on start.|

## Properties

|Name|Description|
|:---|:---|
|[Action](/docs/api/csharp/yarn.unity.legacy.dialogueadvanceinput.action.md)|Gets the  `UnityEngine.InputSystem.InputAction`  configured by this  [DialogueAdvanceInput](yarn.unity.legacy.dialogueadvanceinput.md) .|

