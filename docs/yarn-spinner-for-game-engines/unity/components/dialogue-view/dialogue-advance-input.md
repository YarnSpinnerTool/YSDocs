---
description: >-
  Learn about Dialogue Advance Input, a component that can signal to a Dialogue
  View that the user wants to proceed to the next piece of content.
---

# Dialogue Advance Input

Dialogue Advance Input is a component that receives user input, and uses it to signal to a Dialogue View that the user wants to advance to the next piece of content. Dialogue Advance Input is generally used to implement a 'press spacebar to continue / skip' mechanic.

{% hint style="info" %}
Dialogue Advance Input isn't a Line View itself, but it's designed to work with other line views, to interrupt and control the flow of dialogue.
{% endhint %}

To use a Dialogue Advance Input, create a new game object, and attach a Dialogue Advance Input component to it using the Add Component button.

You can control what specific input the component is looking for by changing the Continue Action Type setting:

* If you set the Continue Action Type to Key Code, you can select a key on the keyboard that will continue to the next line on press.
* If you set the Continue Action Type to Input Action, you can create an Action from an input device (such as from a keyboard, gamepad, or other method).
* If you set the Continue action Type to Input Action from Asset, you can attach an Action from an Input Actions asset that you've set up elsewhere.

{% hint style="info" %}
If you want to use Input Actions, your project will need to be set up to use the new [Unity Input System](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.2/manual/index.html).
{% endhint %}

| Property                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dialogue View             | The [Dialogue View](./) that will be signalled when the user performs the continue action.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Continue Action Type      | <p>A drop-down list that selects how user input will be used to continue to the next line.</p><ul><li>When set to None, the dialogue will not continue based on user input.</li><li>When set to Key Code, the dialogue will continue when the user presses the keyboard key specified in Continue Action Key Code.</li><li>When set to Input System Action, the dialogue will continue when the user performs the Action set up in Continue Action.</li><li>When set to Input System Action from Asset, the dialogue will continue when the user performs the Action specified by the Continue Action Reference field.</li></ul> |
| Continue Action Key Code  | The keyboard key that the user should press to continue to the next line.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Continue Action           | An Input Action that the user should perform to continue to the next line.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Continue Action Reference | An Input Action, stored inside an Input Actions asset, that the user should perform to continue to the next line.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
