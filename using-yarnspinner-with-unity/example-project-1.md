---
description: >-
  This example project demonstrates making a simple dialogue-based game when
  beginning with only an empty Unity scene.
---

# 🛠 Project: Choose-Your-Path Game

## Goals

1. Display Yarn dialogue in a Unity scene
2. Allow a player to select between options to respond
3. Add some static visuals

## Materials

* Yarn Spinner installed in Unity 
* Yarn Spinner set up in a text editor

## Instructions

Open a new Unity 3D project. Ensure Yarn Spinner has been added to the project in the Package Manager as per the [**Installation Instructions**](installation-and-setup.md).

![A new Unity 3D project has been made with no additional changes](../.gitbook/assets/screen-shot-2021-07-05-at-12.59.13-pm.png)

If the sample empty scene is not visible, you'll need to open it. In the **Project Window** where project files are displayed, navigate to **Assets &gt; Scenes** and select **SampleScene.unity**.

### Creating a Runnable Script

Yarn Spinner for Unity comes with a pre-made UI layer and accompanying utility scripts to handle displaying lines and presenting options from Yarn files. In the **Project Window** again, navigate to **Packages &gt; Yarn Spinner &gt; Prefabs** and drag **Dialogue System.prefab** into the scene.

![The Dialogue System has been added from the Project Window into the Scene](../.gitbook/assets/screen-shot-2021-07-05-at-4.35.18-pm%20%281%29.png)

When the **Dialogue System** in the scene is selected, the **Inspector** will display the Yarn Project it is expecting line from. Here, a **Yarn Project** is a kind of linking file that groups Yarn script files together. To make one, navigate to a sensible place for the file to live \(such as a new folder **Assets &gt; Dialogue**\) and right-click the **Project Window** pane to select **Create &gt; Yarn Spinner &gt; Yarn Project**.

{% hint style="info" %}
The existence of Yarn Projects allows larger games with multiple dialogue systems \(e.g. main story dialogue, barks, storylets\) to separate into multiple projects that pass lines to different UI or systems. This allows an extra level of organisation above separate Yarn files which are typically used to separate story scenes or parts.

However, most games will need only a single Yarn Project.
{% endhint %}

Select the scene's **Dialogue System** again and drag the new **Yarn Project** into the labelled slot in the **Inspector**.

![The new Yarn Project has been added to the Dialogue System&apos;s Dialogue Runner](../.gitbook/assets/screen-shot-2021-07-05-at-5.02.12-pm.png)

Now the Yarn Project needs one or more **Yarn Scripts** to get dialogue from. Just like with the Yarn Project, navigate to the desired file location and select **Create &gt; Yarn Spinner &gt; Yarn Script**. Then, with the Yarn Project selected, drag the newly created script into the **Inspector** slot labelled **Source Scripts**. Click **Apply**.

![The new Yarn Script has been added to the Yarn Project&apos;s Source Scripts](../.gitbook/assets/screen-shot-2021-07-05-at-5.10.56-pm.png)

### Filling Out your Script

By default, a new Yarn Script begins with a single empty node with the name of the file. Open the file, rename the node to **Start** and put a single line of test dialogue. You may remove the `tags` field.

```text
title: Start
---
This is a line of test dialogue.
===
```

Returning to Unity, pressing the ▶️ button results in the test line being displayed in front of the empty scene world. Pressing **Continue** will make the UI disappear, as it has reached the end of the script.

![The test line from the Yarn Script has been displayed in the otherwise empty game](../.gitbook/assets/screen-shot-2021-07-05-at-5.30.41-pm.png)

So it's time for the actual writing part. Here, I've opened my new Yarn Script in **Visual Studio Code** with the **Yarn Spinner Extension** installed as per the [**Installation Instructions**](../getting-started/installation-and-setup.md). I've written a simple script about a conversation between a blue sphere 🔵, a red cube 🟥 and the player who plays a shape of their choice. Depending on how the player responds to their greeting, the other shapes will either be pleased to meet them or decide they are rude.

![The new Yarn Script has been given some simple content](../.gitbook/assets/screen-shot-2021-07-06-at-10.13.58-am.png)

You can find this example script below to copy. Or if you need a refresher on how to represent your own story in Yarn, refer to the [**Syntax and File Structure guide**](../getting-started/yarn-syntax-and-file-structure-1/). 

```text
title: Start
---
<<set $shapes_like_you to true>>
Sphere: Hello, I am Blue Sphere.
Cube: Hi there Sphere! I'm Red Cube.
Sphere: And who is this then?

-> I'm Capsule, but my friends call me "Tic Tac". No idea why...
    <<set $name to "Tic Tac">>
-> The name's Triquandle.
    <<set $name to "Triquandle">>
-> Pyramid. Why; who wants to know?
    <<set $name to "Pyramid">>
    <<set $shapes_like_you to false>>
    
<<if $shapes_like_you>>
    Sphere: Nice to meet you {$name}!
    Cube: Yeah, likewise!
<<else>>
    Sphere: No need to be so rude...
    Cube: Yeah, maybe you should be called Grumpy {$name}.
    Sphere: Ha! Totally.
<<endif>>
===
```

Once you've got a basic story, pop back into Unity and check the basics:

* [x] Lines display correctly
* [x] Pressing **Continue** advances lines correctly
* [x] Selecting different options have the expected outcomes

![Yarn Spinner is displaying lines, advancing lines and selecting options correctly as per the script](../.gitbook/assets/screen-shot-2021-07-06-at-10.18.09-am.png)

### Draw the Rest of the Owl

{% hint style="success" %}
Once any desired visual assets have been added to the scene and the story has received any necessary fleshing out, the game is complete. If you've used this example to add dialogue to your own scene, you may skip ahead to **Result**. Otherwise, let's proceed!
{% endhint %}

For the shape example, let's add some "characters" to the scene. Use **Menu &gt; GameObject &gt; 3D Object** to add a Sphere, a Cube and a Plane to the scene. Scale up the Plane by adjusting the vaues in the **Inspector** to `Scale = 10, 10, 10`. To put the Sphere and Cube in front of the camera and make the Plane appear as a floor, they'll need to be moved. The following coordinates are about right, using the default location for the **Main Camera**:

| Object | X | Y | Z |
| :--- | ---: | ---: | ---: |
| Main Camera | 0 | 1 | -10 |
| Sphere | -1 | 1 | -7.5 |
| Cube | 1 | 1 | -7 |
| Plane | 0 | 0.5 | 0 |

Looking to the **Game** view, this should appear as two shapes on a floor with the dialogue UI in front.

![3D Objects have been added to the Scene to act as characters](../.gitbook/assets/screen-shot-2021-07-06-at-10.45.52-am.png)

All this white makes them difficult to distinguish though, so let's colour each Object. Create basic **Materials** for each by right-clicking the **Project Window** in the desired file location and select **Create &gt; Material** three times. Change the colour of each Material to three distinct colours by modifying the **Albedo** value in the **Inspector**.

Add a Material to each Object by selecting the desired object and dragging the Material into the **Materials &gt; Element 0** under **Mesh Renderer** in the **Inspector**.

![Materials have been added to the 3D Objects in the Scene](../.gitbook/assets/screen-shot-2021-07-06-at-10.52.48-am.png)

{% hint style="info" %}
This tutorial isn't here to teach you all of Unity. If you need some guidance about aspects outside of Yarn Spinner, you can [**check out our books on the topic**](https://secretlab.games/books) or there are lots of helpful guides around the web, on YouTube, or created by Unity themselves!
{% endhint %}

## Result

A playable branching story game with simple static visuals.

![The game is complete and playable with visuals](../.gitbook/assets/screen-shot-2021-07-06-at-10.54.38-am.png)

An easy way to spice this up is to just add more dialogue with the same characters. Here is an example script that shows how a simple starter script made for testing can grow to a fuller conversation. And it doesn't stop there! Yarn Spinner is perfect for allowing growing projects to remain functional throughout.

```text
title: Start
---
<<set $shapes_like_you to true>>
Sphere: Hello, I am Blue Sphere.
Cube: Hi there Sphere! I'm Red Cube.
Sphere: And who is this then?

-> I'm Capsule, but my friends call me "Tic Tac". No idea why...
    <<set $name to "Tic Tac">>
-> The name's Triquandle.
    <<set $name to "Triquandle">>
-> Pyramid. Why; who wants to know?
    <<set $name to "Pyramid">>
    <<set $shapes_like_you to false>>
    
<<if $shapes_like_you>>
    Sphere: Nice to meet you {$name}!
    Cube: Yeah, likewise!
    Cube: Do you wanna play a game?
    -> Yeah, sure!
        Sphere: Let's play Two Truths and a Lie then!
        <<jump TwoTruthsGame>>
    -> Ugh, no.
<<endif>>
// if they didn't offer to play a game, or they did but you said no,
// then they don't like you now
<<jump BadEnding>>
===
title: TwoTruthsGame
---
<<set $rounds_won to 0>>
Cube: I'll go first! Hmmm...
Cube: I have 6 faces. I have 12 edges. My favourite colour is blue.
Cube: What do you think is the lie?
-> The number of faces.
-> The one about edges.
-> Your favourite colour, obviously.
    <<set $rounds_won += 1>>
Sphere: I agree.

<<if $rounds_won > 0>>
    Cube: You're too smart!
<<else>>
    Cube: Wrong! Haha
<<endif>>
Cube: Of course my favourite colour is red!

Sphere: My turn!
Sphere: I am oblate. I am prolate. I am neither.
-> The first one.
-> The second one.
-> The neither.
-> Hang on, that doesn't work.
    That's two lies and one truth!
    <<set $rounds_won += 1>>
Sphere: Oh wait, I think I've mucked it up...

<<if $rounds_won == 2>>
    Cube: You won both rounds, congrats!
<<elseif $rounds_won == 1>>
    Cube: Well, at least you got one right.
<<else>>
    Sphere: At least we both lost together.
<<endif>>

-> That was great!
    <<jump GoodEnding>>
-> This game is lame.
    <<jump BadEnding>>
===
title: GoodEnding
---
Cube: I think we're friends now.
Sphere: Agreed.
Cube: What do you think, {$name}?
-> BFFs, for sure!
-> As if I'd be friends with you two!
    <<jump BadEnding>>
===
title: BadEnding
---
Sphere: No need to be so rude...
Cube: Yeah, maybe you should be called Grumpy {$name}.
Sphere: Ha! Totally.
===
```

Now, let's move onto an example where Yarn Spinner leverages the power of Unity to change things in the scene as well as running dialogue...

