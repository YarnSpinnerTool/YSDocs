---
description: >-
  This example project demonstrates making a simple dialogue-based game when
  beginning with some character and location assets.
---

# 📝 Example Project 2

## Goals

1. Display Yarn dialogue in a Unity scene
2. Allow a player to select between options to respond
3. Use Yarn Spinner to trigger commands that change the scene, camera and characters

## Materials

* Yarn Spinner installed in Unity
* Yarn Spinner set up in a text editor
* **Starter Asset Package** downloaded and unzipped

## Instructions

Open a new Unity 3D project. Ensure Yarn Spinner has been added to the project in the Package Manager as per the [**Installation Instructions**](installation-and-setup.md).

![](../.gitbook/assets/screen-shot-2021-07-05-at-12.59.13-pm.png)

Drag the provided Asset Package into the **Project Window** where project files are displayed in Unity to import them into the project.

![The provided assets are being imported](../.gitbook/assets/screen-shot-2021-07-06-at-11.15.32-am.png)

To see the **Scene** containing the imported assets, you'll need to open it. In the **Project Window**, navigate to **Assets &gt; Scenes** and select **Start Point.unity**.

This package comes with three main things: 

1. character models for three different humans in spacesuits, 
2. a simple environment styled like the inside of a spaceship, and 
3. some basic C\# utility scripts that will be covered in more detail shortly.

The important part to know is that in the **Scene** there are a number of named but invisible markers—Game Objects with no model attached—that just store a location and a facing. These will be used as anchors to move other models around by sending them to markers based on name.

![](../.gitbook/assets/spaceship.png)

You can see these yourself in Unity by selecting each marker and allocating them an Icon using the dropdown at the top of the **Inspector**. The markers named `Camera` are the camera markers and the ones named like `CorridorLeft` or `BridgeRight` are Character markers.

![Camera markers have been assigned &#x1F536; icons and Character markers &#x1F535; icons](../.gitbook/assets/screen-shot-2021-07-06-at-11.40.15-am.png)

### Creating a Runnable Script

{% hint style="success" %}
The next step is to import the Dialogue System and hook up a Yarn Project and Yarn Script. If you have completed [**Example Project 1**](example-project-1.md) before, you may skip ahead to **Adding Commands**. Otherwise, let's proceed!
{% endhint %}

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

By default, a new Yarn Script begins with a single empty node with the name of the file.

### Adding Commands



## Result

A playable visual novel-type game with multiple characters and scenes and sensible transitions between them.

