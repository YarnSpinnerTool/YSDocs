---
description: >-
  This example project demonstrates making a simple dialogue-based game when
  beginning with only an empty Unity scene.
icon: face-smile-hearts
---

# Your First Yarn Spinner Game

## Goals

1. Display Yarn dialogue in a Unity scene
2. Allow a player to select between options to respond
3. Add some static visuals

## Preparation

* Yarn Spinner installed in Unity: [installation-and-setup](installation-and-setup/ "mention")
* Yarn Spinner set up in a text editor: [yarn-spinner-editor](../write-yarn-scripts/yarn-spinner-editor/ "mention")

## Instructions

Open a new Unity 3D project. Ensure Yarn Spinner has been added to the project in the Package Manager as per the [**Installation Instructions**](installation-and-setup/).

![A new Unity 3D project has been made with no additional changes](<../.gitbook/assets/Screenshot 2025-04-11 at 12.54.32.png>)

If the sample empty scene is not visible, you'll need to open it. In the **Project Window** where project files are displayed, navigate to **Assets > Scenes** and select **SampleScene.unity**.

### Creating a Runnable Script

Yarn Spinner for Unity comes with a pre-made UI layer and accompanying utility scripts to handle displaying lines and presenting options from Yarn files. Add one by opening the **GameObject menu**, and choosing **Yarn Spinner > Dialogue System**.

{% hint style="info" %}
Depending on your version of Unity, a window might appear asking you to import TextMesh Pro assets. If this appears, click 'Import TMP Essentials'.
{% endhint %}

![The Dialogue System has been added to the Scene](<../.gitbook/assets/Screenshot 2025-04-11 at 12.59.13.png>)

When the **Dialogue System** in the scene is selected, the **Inspector** will display the Yarn Project it is expecting line from. Here, a **Yarn Project** is a kind of linking file that groups Yarn script files together.

To make one, navigate to a sensible place for the file to live (such as a new folder **Assets > Dialogue**) and right-click the **Project Window** pane to select **Create > Yarn Spinner > Yarn Project**.

{% hint style="info" %}
The existence of Yarn Projects allows larger games with multiple dialogue systems (e.g. main story dialogue, barks, storylets) to separate into multiple projects that pass lines to different UI or systems.&#x20;

This allows an extra level of organisation above separate Yarn files which are typically used to separate story scenes or parts. However, most games will need only a single Yarn Project.
{% endhint %}

Select the scene's **Dialogue System** again and drag the new **Yarn Project** into the labelled slot in the **Inspector**.

![The new Yarn Project has been added to the Dialogue System's Dialogue Runner](<../.gitbook/assets/Screenshot 2025-04-11 at 13.08.32.png>)

Now the Yarn Project needs one or more **Yarn Scripts** to get dialogue from. Just like with the Yarn Project, navigate to the desired file location and select **Create > Yarn Spinner > Yarn Script**. Name the new script **Start**, and place it in the same folder as the Yarn Project. This will make the Yarn Script be included in the Yarn Project.

![The new Yarn Script has been added to the Yarn Project's Source Scripts](<../.gitbook/assets/Screenshot 2025-04-11 at 13.22.57.png>)

### Filling Out Your Script

By default, a new Yarn Script begins with a single node that has the same name as the file. It will contain a single line of placeholder dialogue.

```
title: Start
---
This is an example of a Yarn Spinner script. Write your dialogue here!
===
```

To set this dialogue to run automatically when the game starts, select the **Dialogue System** again and in the Dialogue Runner section of the inspector check **Start Automatically**. The default start node name is called Start, which matches the node created earlier.

Now, pressing the ▶️ button in Unity should result in the test line being displayed in front of the empty scene world. Pressing the **Continue** arrow will make the UI disappear, as it has reached the end of the script.

![The placeholder line from the Yarn Script has been displayed in the otherwise empty game](<../.gitbook/assets/Screenshot 2025-04-11 at 13.28.30.png>)

So it's time for the actual writing part. Here, I've opened my new Yarn Script in **Visual Studio Code** with the **Yarn Spinner Extension** installed as per the [**Installation Instructions**](../write-yarn-scripts/yarn-spinner-editor/). I've written a simple script about a conversation between the player and a capsule-shaped NPC named Capsley. Depending on how the player responds to their greeting, Mr Capsley will either be pleased to meet them or decide they are rude.

You can find this example script below to copy. Or if you need a refresher on how to represent your own story in Yarn, refer to the [**Syntax Guide**](../write-yarn-scripts/scripting-fundamentals/lines-nodes-and-options.md).

```
title: Start
---
/// Whether Capsley like you or not. This starts true, but may change.
<<declare $capsley_likes_you = true as bool>>
/// The player's name. The player chooses this. It starts empty.
<<declare $player_name = "" as string>>

Capsley: Hello, I am Mr Capsley.
Capsley: Who are you then?

-> I'm Capsule, but my friends call me "Tic Tac". No idea why...
    <<set $player_name to "Tic Tac">>
-> The name's Triquandle.
    <<set $player_name to "Triquandle">>
-> Pyramid. Why - who wants to know?
    <<set $player_name to "Pyramid">>
    <<set $capsley_likes_you to false>>

<<if $capsley_likes_you>>
    Capsley: Nice to meet you {$player_name}!
<<else>>
    Capsley: No need to be so rude...
    Capsley: Maybe you should be called Grumpy {$player_name}.
<<endif>>
===
```

Once you've got a basic story, pop back into Unity and check the basics:

* [x] Lines display correctly
* [x] Pressing the continue arrow advances lines correctly
* [x] Selecting different options have the expected outcomes

![Yarn Spinner is displaying lines, advancing lines and selecting options correctly as per the script](<../.gitbook/assets/Screenshot 2025-04-11 at 13.39.47.png>)

### Draw the Rest of the Owl

{% hint style="success" %}
Once any desired visual assets have been added to the scene and the story has received any necessary fleshing out, the game is complete. If you've used this example to add dialogue to your own scene, you may skip ahead to [**Result**](example-project-1.md#result). Otherwise, let's proceed!
{% endhint %}

For the shape example, let's add a "character" to the scene. Use **Menu > GameObject > 3D Object** to add a Capsule to the scene. Name him **Capsley**. For the camera to look at him properly, we'll want to set his transform position to `x = 0, y = 1, z = -8`. You should now be looking at him up close.

![A capsule has been added to the Scene to act as our Capsley character](<../.gitbook/assets/Screenshot 2025-04-11 at 13.45.54.png>)

All this grey in the skybox makes him difficult to distinguish though, and he doesn't look very friendly. Create a basic **Materials** for him by right-clicking the **Project Window** in the desired file location and select **Create > Material**. Change the colour of the Material to your preferred hue by modifying the **Base map** value in the **Inspector**.

Add the Material to each Capsley by selecting him in the Scene Heirarchy and dragging the new Material into the **Materials > Element 0** in the **Mesh Renderer** part of the **Inspector**.

![A Material has been added to Capsley in the Scene](<../.gitbook/assets/Screenshot 2025-04-11 at 13.49.57.png>)

By creating a new material to be layered on top, we can give poor Capsley a face. Here, a PNG has been added to the Unity project and used as the **Base map** instead of a flat colour. By selecting **Alpha clipping**, it can be added to Capsley's **Materials > Element 1** (you'll need to add this element) without removing his base colour.

{% hint style="info" %}
This tutorial isn't here to teach you all of Unity. If you need some guidance about aspects outside of Yarn Spinner, you can [**check out our books on the topic**](https://secretlab.games/books) or there are lots of helpful guides around the web, on YouTube, or created by Unity themselves!
{% endhint %}

## Result

A playable branching story game with simple static visuals.

![The game is complete and playable with visuals](<../.gitbook/assets/Screenshot 2025-04-11 at 14.17.46.png>)

An easy way to spice this up is to just add more dialogue or more characters. And it doesn't stop there! Yarn Spinner is perfect for allowing growing projects to remain functional throughout.
