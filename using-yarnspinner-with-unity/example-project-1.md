---
description: >-
  This example project demonstrates making a simple dialogue-based game when
  beginning with only an empty Unity scene.
---

# 📝 Example Project 1

## Goals

1. Display Yarn dialogue in a Unity scene
2. Allow a player to select between options to respond

## Materials

* Yarn Spinner installed in Unity 
* Yarn Spinner set up in a text editor

## Instructions

Open a new Unity 3D project. Ensure Yarn Spinner has been added to the project in the Package Manager as per the [**Installation Instructions**](installation-and-setup.md).

![A new Unity 3D project has been made with no additional changes](../.gitbook/assets/screen-shot-2021-07-05-at-12.59.13-pm.png)

If the sample empty scene is not visible, you'll need to open it. In the **Project Window** where project files are displayed, navigate to **Assets &gt; Scenes** and select **SampleScene.unity**.

Yarn Spinner for Unity comes with a pre-made UI layer and accompanying utility scripts to handle displaying lines and presenting options from Yarn files. In the **Project Window** again, navigate to **Packages &gt; Yarn Spinner &gt; Prefabs** and drag **Dialogue System.prefab** into the scene.

![The Dialogue System has been added from the Project Window into the Scene](../.gitbook/assets/screen-shot-2021-07-05-at-4.35.18-pm%20%281%29.png)

When the **Dialogue System** in the scene is selected, the **Inspector** will display the Yarn Project it is expecting line from. Here, a **Yarn Project** is a kind of linking file that groups Yarn script files together. To make one, navigate to a sensible place for the file to live \(such as a new folder **Assets &gt; Dialogue**\) and right-click the **Project Window** pane to select **Create &gt; Yarn Spinner &gt; Yarn Project**.

{% hint style="info" %}
The existence of Yarn Projects allows larger games with multiple dialogue systems \(e.g. main story dialogue, barks, storylets\) to separate into multiple projects that pass lines to different UI or systems. This allows an extra level of organisation above separate Yarn files which are typically used to separate story scenes or parts.

However, most games will need only a single Yarn Project.
{% endhint %}

Select the scene's **Dialogue System** again and drag the new **Yarn Project** into the labelled slot in the Inspector.

![The new Yarn Project has been added to the Dialogue System&apos;s Dialogue Runner](../.gitbook/assets/screen-shot-2021-07-05-at-5.02.12-pm.png)

Now the Yarn Project needs one or more **Yarn Scripts** to get dialogue from. Just like with the Yarn Project, navigate to the desired file location and select **Create &gt; Yarn Spinner &gt; Yarn Script**. Then, with the Yarn Project selected, drag the newly created script into the Inspector slot labelled **Source Scripts**. Click **Apply**.

![The new Yarn Script has been added to the Yarn Project&apos;s Source Scripts](../.gitbook/assets/screen-shot-2021-07-05-at-5.10.56-pm.png)

By default, a new Yarn Script begins with a single empty node with the name of the file. Open the file, rename the node to **Start** and put a single line of test dialogue. 

```text
title: Start
tags:
---
This is a line of test dialogue.
===
```

Returning to Unity, pressing the ▶️ button results in the test line being displayed in front of the empty scene world. Pressing **Continue** will make the UI disappear as it has reached the end of the script.

![The test line from the Yarn Script has been displayed in the otherwise empty game](../.gitbook/assets/screen-shot-2021-07-05-at-5.30.41-pm.png)

So it's time for the actual writing part. Here, I've opened my new Yarn Script in **Visual Studio Code** with the **Yarn Spinner Extension** installed as per the [**Installation Instructions**](../getting-started/installation-and-setup.md). I've written a simple script about a conversation between a blue sphere 🔵, a red cube 🟥 and the player who plays a shape of their choice. It has some simple branching options that end up with either all the shapes becoming friends, or the player being rude and getting left out.

![The new Yarn Script has been given some simple content](../.gitbook/assets/screen-shot-2021-07-05-at-5.23.56-pm.png)

If you need a refresher on how to represent your story in Yarn, pop back to the [**Syntax and File Structure guide**](../getting-started/yarn-syntax-and-file-structure-1/).

## Result

A playable branching story game.



