---
description: Quickly get started with a simple scene.
icon: star-shooting
---

# Unity Quick Start

Want to use Yarn Spinner in a new scene right away? Follow these steps.

### Setting Up A Demo Scene

1. **Create a new empty Unity project**, by following [the instructions in the Unity manual](https://docs.unity3d.com/Manual/GettingStarted.html).
2. **Install Yarn Spinner into the project**, by following the instructions in [installation-and-setup.md](installation-and-setup.md "mention").
3. **Add a Dialogue System to the scene:**, by opening the GameObject menu and choosing Yarn Spinner -> Dialogue System.
4. **Create a new** [**Yarn script**](importing-yarn-files/yarn-scripts.md), by opening the Assets menu and choosing Create -> Yarn Spinner -> Yarn Script. Name the new file `HelloYarn`.
5. **Open the new Yarn script** by double-clicking it.
   1. Select all of the text in the file, and delete it.
   2. Copy the text below, and paste it into the file.

```
title: Start
---
Wow!
My first ever Yarn script in Unity!

-> Gosh!
-> Incredible!
-> I'm amazed!

Anyway, time to get writing!
===
```

{% hint style="info" %}
You can learn about our recommended editor, Visual Studio Code with the official Yarn Spinner Extension at: [editing-with-vs-code](../write-yarn-scripts/syntax-basics/editing-with-vs-code/ "mention").
{% endhint %}

1. **Save the file and return to Unity.**
2. **Create a new** [**Yarn Project**](importing-yarn-files/yarn-projects.md) **that uses this script**, by selecting the `HelloYarn` file, and clicking the Create New Yarn Project button in the Inspector. This will create a new Yarn Project called `Project`. Projects are collections of Yarn scripts that get compiled together, and can be used with a Dialogue Runner.
3. **Make the Dialogue Runner use the Project** by dragging the Project you just made into the Dialogue Runner's Yarn Project field.
4. **Play the game** by clicking the Play button at the top of the window. Your dialogue will appear!
