# DialogueAdvanceInput

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

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
via the <a href="yarn.unity.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a> field.</p> <p>When the configured input occurs, this component calls the <a href="yarn.unity.dialogueviewbase.userrequestedviewadvancement.md">UserRequestedViewAdvancement()</a> method on its
<a href="yarn.unity.dialogueadvanceinput.dialogueview.md">dialogueView</a>.
</p>

## Enums

|Name|Description|
|:---|:---|
|[ContinueActionType](/docs/api/csharp/yarn.unity.dialogueadvanceinput.continueactiontype-1.md)|The type of input that this component is listening for in order to signal that its dialogue view should advance.|
|[ContinueButtonActionType](/docs/api/csharp/yarn.unity.dialogueadvanceinput.continuebuttonactiontype.md)|The button/keycode action type, should the button be fired on release or press?|

## Fields

|Name|Description|
|:---|:---|
|[continueAction](/docs/api/csharp/yarn.unity.dialogueadvanceinput.continueaction.md)|The  <code>UnityEngine.InputSystem.InputAction</code>  that this component is listening for.|
|[continueActionButtonName](/docs/api/csharp/yarn.unity.dialogueadvanceinput.continueactionbuttonname.md)|The virtual button that this component is listening for.|
|[continueActionKeyCode](/docs/api/csharp/yarn.unity.dialogueadvanceinput.continueactionkeycode.md)|The keyboard key that this component is listening for.|
|[continueActionOnButtonRelease](/docs/api/csharp/yarn.unity.dialogueadvanceinput.continueactiononbuttonrelease.md)|Should the continue action respond to key being pressed down or released.|
|[continueActionReference](/docs/api/csharp/yarn.unity.dialogueadvanceinput.continueactionreference.md)|An  <code>UnityEngine.InputSystem.InputActionReference</code>  that refers to the action that this component is listening for.|
|[continueActionType](/docs/api/csharp/yarn.unity.dialogueadvanceinput.continueactiontype-2.md)|The type of input that this component is listening for.|
|[dialogueView](/docs/api/csharp/yarn.unity.dialogueadvanceinput.dialogueview.md)|The dialogue view that will be notified when the user performs the advance input (as configured by  <a href="yarn.unity.dialogueadvanceinput.continueactiontype-2.md">continueActionType</a>  and related fields.)|
|[enableActionOnStart](/docs/api/csharp/yarn.unity.dialogueadvanceinput.enableactiononstart.md)|Configures whether  <a href="yarn.unity.dialogueadvanceinput.action.md">Action</a>  should be enabled on start.|

## Properties

|Name|Description|
|:---|:---|
|[Action](/docs/api/csharp/yarn.unity.dialogueadvanceinput.action.md)|Gets the  <code>UnityEngine.InputSystem.InputAction</code>  configured by this  <a href="yarn.unity.dialogueadvanceinput.md">DialogueAdvanceInput</a> .|

