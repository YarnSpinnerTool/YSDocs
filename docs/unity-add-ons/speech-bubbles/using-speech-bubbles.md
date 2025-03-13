---
description: >-
  Learn how to use the Speech Bubbles, from the Speech Bubbles for Yarn Spinner
  Add-On Package.
---

# Using Speech Bubbles

The Speech Bubbles Add-On provides a flexible speech bubble system with a variety of possible customisations. Here, you'll learn how to implement it in a Unity project by looking at a _super simple_ side-scrolling game.

## Setting up for Speech Bubbles

To use Speech Bubbles for Yarn Spinner, you'll need to create a new Unity project and [install he Yarn Spinner package](../../yarn-spinner-for-unity/installation-and-setup.md), and then [install the Speech Bubbles for Yarn Spinner package](installing-speech-bubbles.md).

For this guide, we'll assume you've made a simple 2D side-scrolling environment, much like this:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-21 at 4.22.33 pm.png" alt=""><figcaption></figcaption></figure>

Our environment is nothing more than some sprites (from the GameObject menu -> 2D Object -> Sprites)—a Square, resized to be the floor, and two capsules—and a simple player movement script.&#x20;

With a project ready, [install the Speech Bubbles for Yarn Spinner package](installing-speech-bubbles.md), and install TextMesh Pro (TMP) if prompted. You'll also need to install the Unity Input System Package.

{% hint style="info" %}
You can find the Unity Input System Package in the Unity Package Manager, found in the Window menu -> Package Manager. For further guidance, visit [the Unity documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.7/manual/Installation.html#installing-the-package).&#x20;
{% endhint %}

#### Creating a Dialogue Runner

Add an empty GameObject to your Hierarchy, and name it `Dialogue System`. Use the Add Component button in the Inspector to add a Dialogue Runner component and a In Memory Variable Storage component to it:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-21 at 5.14.21 pm.png" alt="" width="375"><figcaption></figcaption></figure>

Then, in the Hierarchy, add a Canva as a child object, as well as a new empty GameObject named `Bubble View`. Select the `Bubble View` and use the Add Component button in its Inspector to add a Bubble Dialogue View component:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-21 at 4.36.14 pm.png" alt="" width="563"><figcaption></figcaption></figure>

Next, make a new Yarn project in the Assets pane, give it a Yarn Script, and add the new project to the Dialogue Runner in the Inspector.

Our demonstration here uses the following `.yarn` script:

<details>

<summary>Simple Yarn Script</summary>

```
title: Start
---
Orange: Hello!
    -> Hi!
        Orange: Hello.
    -> Who are you?
        Orange: I'm Orange.
    -> You're orange.
        Orange: Yep.
===

```

</details>

Make sure the Start Node in the Dialogue System's Inspector is set to `Start`, and that Start Automatically is chosen.

Next, expand the Dialogue Views section of the Dialogue System's Inspector, set the number of Diloague Views to `1`, and drag the BubbleView GameObject from the Hierarchy (it should be a child of the Dialogue System) into the slot:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 11.44.50 am.png" alt="" width="563"><figcaption></figcaption></figure>

### Adding Bubbles to Characters

Our simple 2D side-scrolling environment has two characters in it: a Player Character, and a Orange NPC. In this case, we want things that the player can choose from to come out of bubbles attached to the Player Character, and we want the NPCs responses to come out of the NPC.

To allow this to happen, we must specify the position that the bubbles will be anchored to, for each character. To do this for the Orange NPC, select them in the Hierarchy, and add an empty GameObject as a child. Name it Bubble Anchor:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 11.56.37 am.png" alt="" width="525"><figcaption></figcaption></figure>

Select the BubbleAnchor in the Hierarchy, and position it above the character, wherever you want the bubble to be anchored:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 12.22.13 pm.png" alt="" width="375"><figcaption></figcaption></figure>

Next, create a new Basic Character Bubble Data asset, in the Project pane:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 12.24.18 pm.png" alt="" width="563"><figcaption></figcaption></figure>

Name the new asset Bubble Data, or similar. Select it, and use the Inspector to set the Text Color to black. Then, select the Character in the Hierarchy and use its Inspector's Add Component button to add a Character Bubble Anchor component:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-21 at 4.37.52 pm.png" alt="" width="563"><figcaption></figcaption></figure>

Use the Inspector on the Orange NPC to set the Character Name (ours is called "Orange"), drag the Bubble Anchor child object from Hierarchy to the Bubble Position slot, and drag the Bubble Data asset from the Project pane to the Character Bubble Data slot:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 12.34.53 pm.png" alt="" width="563"><figcaption></figcaption></figure>

Add a Bubble Anchor child object to the Player Character as well, and position it appropriately. Then, use the Add Component button in the Player Character's Inspector to add three components: a _Character Bubble Anchor_ component, a _Sample Bubble Option_ Input component, and a _Player Input_ component.

Set the Character Name to something appropriate (in the case of the Player Character, "Player" is a good idea), assign the Player Character's Bubble Anchor to the Bubble Position slot, and assign the same Bubble Data asset you used for the Orange NPC to the Character Bubble Data slot:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 12.42.28 pm.png" alt="" width="561"><figcaption></figcaption></figure>

To allow the input to be controlled by the player, create an [Input Actions Asset](https://docs.unity3d.com/Packages/com.unity.inputsystem@0.9/manual/ActionAssets.html), name it Dialogue Actions, and double-click it to bring up Action Editor. Use the Action Editor to create an Action Map for Dialogue, and then add an Action called `ActionDialogue`, and bind it to something appropriate (such as the Space key):

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 12.46.43 pm.png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
You can learn more about Input Actions [in the Unity documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@0.9/manual/ActionAssets.html).
{% endhint %}

Expand the new asset in the Project pane so you can see the specific action that you just made:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 12.48.39 pm.png" alt="" width="371"><figcaption></figcaption></figure>

In the Sample Bubble Option Input component, assign the Advance Dialogue action to the Advance Dialogue Action slot (by dragging it from the expanded Input Actions Asset in the Project pane), and drag the Bubble View from the Dialogue System (in the Hiearachy) into the Bubble Dialogue View slot:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 12.53.46 pm.png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="warning" %}
The Sample Bubble Option Input script comes with Speech Bubbles for Yarn Spinner. You can find it in`Speech Bubbles for Yarn Spinner/Examples/Shared Example Resources`. The script gives you basic input handling to allow the player to select and change options for their dialogue. It's not intended to be used or even subclassed, and is solely provided for samples and examples. In a game, your game's input system should handle this.
{% endhint %}

In the Player Input component, drag the overall Dialogue Actions asset from the Project pane into the Actions slot, and drag your camera from the Hierarchy into the Camera slot, and set the Behavior dropdown to Invoke C Sharp Events:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 12.53.51 pm.png" alt="" width="563"><figcaption></figcaption></figure>

The Player Input component needs to have its behavior setting changed to _Invoke C Sharp Events_ because Yarn Spinner uses C# Events, rather than Unity's own event system.

{% hint style="info" %}
The Player Input component is part of Unity's Input System. You can learn more about it [in the Unity documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.7/manual/PlayerInput.html).
{% endhint %}

## Playing with Bubbles

With that, you can play your project and see the Speech Bubbles in action:

<figure><img src="../../.gitbook/assets/demo.gif" alt=""><figcaption></figcaption></figure>

Next check our provided [Speech Bubble Examples](speech-bubble-examples.md).
