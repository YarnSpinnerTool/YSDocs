---
description: >-
  Learn about the Line Advancer, a component that can signal to a Dialogue
  Presenter that the user wants to proceed to the next piece of content.
---

# Line Advancer

A **Line Advancer** listens for user input and sends requests to a Dialogue Runner to advance the presentation of the current line, either by asking a dialogue runner to hurry up its delivery, advance to the next line, or cancel the entire dialogue session.

A Line Advancer is generally used to implement a 'press spacebar to continue/skip' mechanic.

{% hint style="info" %}
A Line Advancer isn't a Line Presenter itself, but it's designed to work with other line presenters, to interrupt and control the flow of dialogue.
{% endhint %}

To use a Line Advancer, create a new game object, and attach a Line Advancer component to it using the Add Component button.

You can control what specific input the component is looking for by changing the Continue Action Type setting:

* If you set the **Input Mode** to **Key Code**, you can select a key on the keyboard that will continue to the next line on press, or hurry up.
* If you set the **Input Mode** to **Input Actions**, you can create an Action from an input device (such as from a keyboard, gamepad, or other method).

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-15 at 1.45.50 pm.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
If you want to use Input Actions, your project will need to be set up to use the  [Unity Input System](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.2/manual/index.html).
{% endhint %}

| Property                                                                       | Description                                                                          |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| Runner                                                                         | The Dialogue Runner that will receive requests to advance or cancel content          |
| Multi Advance Is Cancel                                                        | Does repeatedly requesting a line advance cancel the line?                           |
| Advance Count (available if Multi Advance is Cancel is chosen)                 | The number of times that a line advance occurs before the current line is cancelled. |
| Input Mode                                                                     | The type of input that this line advancer responds to.                               |
| Hurry Up Line Key Code or Action (available depending on choice of Input Mode) | Tell the advance to hurry up.                                                        |
| Next Line Key Code or Action (available depending on choice of Input Mode)     | Force the next line.                                                                 |
| Cancel Dialogue Key Code (available depending on choice of Input Mode)         | Cancel dialogue.                                                                     |
