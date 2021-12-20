---
description: Quickly get started with a simple scene.
---

# ⚡ Quick Start

Want to use Yarn Spinner in a new scene right away? Follow these steps.

### Setting Up A Demo Scene

1. **Create a new empty Unity project**, by following [the instructions in the Unity manual](https://docs.unity3d.com/Manual/GettingStarted.html).
2. **Install Yarn Spinner into the project**, by following the instructions in [installation-and-setup.md](installation-and-setup.md "mention").&#x20;
3. **Add the Dialogue System prefab to the scene:**
   1. In the Project pane, scroll down to the Yarn Spinner folder. You'll find it in the Packages section.
   2. Inside the Yarn Spinner folder, open the Prefabs folder, and locate the Dialogue System prefab.
   3. Drag the Dialogue System into your scene.
4. **Create a new** [**Yarn script**](importing-yarn-files/yarn-scripts.md), by opening the Assets menu and choosing Create -> Yarn Spinner -> Yarn Script. Name the new file `HelloYarn`.
5. **Open the new Yarn script** by double-clicking it.&#x20;
   1. Select all of the text in the file, and delete it.&#x20;
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

1. **Save the file and return to Unity.**
2. **Create a new** [**Yarn Project**](importing-yarn-files/yarn-projects.md) **that uses this script**, by selecting the `HelloYarn` file, and clicking the Create New Yarn Project button in the Inspector. This will create a new Yarn Project called `Project`.
3. **Attach the Yarn Project to the Dialogue Runner**, by selecting the Dialogue Runner in the Hierarchy, and dragging the `Project` into the Yarn Project field.
4. **Play the game** by clicking the Play button at the top of the window. Your dialogue will appear!
