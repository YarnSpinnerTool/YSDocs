---
description: Quickly get started with a simple scene.
icon: star-shooting
---

# Unity Quick Start

{% hint style="danger" %}
Want to use Yarn Spinner in a new scene in Unity right away? Follow these steps. If this is your first time using Yarn Spinner, or you're a bit unsure how it all works, we suggest reading the rest of the documentation first!
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=OoVBRmeUYMA&t=1s" %}

## &#x20;Basic Yarn Spinner for Unity Usage

1. **Install Unity 2022.3 or newer**.
2. **Create a new empty Unity project**, by following [the instructions in the Unity manual](https://docs.unity3d.com/Manual/GettingStarted.html).
3. **Install Yarn Spinner into the project**, by following the instructions in [.](./ "mention").
4. **Add a Dialogue System to the scene:**, by opening the GameObject menu and choosing Yarn Spinner -> Dialogue System.
5. **Create a new** **Yarn Spinner Script**, by opening the Assets menu and choosing Create -> Yarn Spinner -> Yarn Script. Name the new file `HelloYarn`.
6. **Open the new Yarn script** by double-clicking it.
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
You can learn about our recommended editor, Visual Studio Code with the [Yarn Spinner for Visual Studio Code extension](../../write-yarn-scripts/yarn-spinner-editor/).
{% endhint %}

7. **Save the file and return to Unity.**
8. **Create a new** [**Yarn Project**](../yarn-projects.md) **that uses this script**, by selecting the `HelloYarn` file, and clicking the Create New Yarn Project button in the Inspector. This will create a new Yarn Project called `Project`. Projects are collections of Yarn scripts that get compiled together, and can be used with a Dialogue Runner.
9. **Make the Dialogue Runner use the Project** by dragging the Project you just made into the Dialogue Runner's Yarn Project field.
10. **Play the game** by clicking the Play button at the top of the window. Your dialogue will appear!
