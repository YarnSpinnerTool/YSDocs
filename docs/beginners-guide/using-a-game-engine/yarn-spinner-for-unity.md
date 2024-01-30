---
description: >-
  The third step in our beginner's guide, focusing on getting up and running
  with Yarn Spinner for Unity.
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
---

# Yarn Spinner for Unity

This step of the beginner's guide helps you move from writing Yarn scripts outside of a game engine, to initial integration steps to turn them into a game with Unity.

First, launch the Unity Hub, and create a new project for Unity 2021.3 or newer.&#x20;

## Installing Yarn Spinner for Unity

In the new empty project, open the Edit menu -> Project Settings..., and choose the Package Manager section in the left column of the Project Settings window that appears.&#x20;

In the middle area of the window, add an entry named `OpenUPM`, with the URL set to `https://package.openupm.com`, and the Scopes set to `dev.yarnspinner`. Then, click Save.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 11.41.29 am.png" alt=""><figcaption><p>Adding OpenUPM, the Package Registry that distributes Yarn Spinner for Unity, to your Unity project.</p></figcaption></figure>

This process adds the OpenUPM Package Registry, which is one of the ways we distribute the offical Yarn Spinner for Unity package.&#x20;

{% hint style="info" %}
We recommend sticking with the Beginner's Guide for your first use of Yarn Spinner for Unity, but if you thirst to learn more, you can explore other ways to install Yarn Spinner for Unity at: [Installation for Unity](../../using-yarnspinner-with-unity/installation-and-setup.md).&#x20;
{% endhint %}

With the OpenUPM Package Registry added to the project, you can close the Project Settings window and open the Window menu -> Package Manager. In the Package Manager window that appears, choose the Packages dropdown, and change the view to Packages: My Registries.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 11.45.05 am.png" alt=""><figcaption><p>Changing the packages displayed to you in the Package Manager to the ones in registries you've added.</p></figcaption></figure>

This will show the packages available from the registry (and scope) that you just added, which is likely to only be Yarn Spinner at this point. Select the Yarn Spinner package from the column on the left of the Package Manager window, and click the Install button found on the bottom right. Yarn Spinner for Unity will be downloaded and installed inside your project.

## Using Yarn Spinner for Unity

Yarn Spinner for Unity provides a way to get the contents of your Yarn scripts into Unity, which allows you to construct a game around your dialogue. This beginner's guide shows guides you through one simple way of using Yarn Spinner for Unity to do this.

The provided Yarn Spinner views use the Unity package TextMesh Pro to display text. This means you will need to install it before using Yarn Spinner. To do this, open the Window menu and choose -> TextMesh Pro -> Import TMP Essential Resources.

{% hint style="info" %}
If you work with a preexisting game that you're adding Yarn Spinner to, you may already have TextMesh Pro in your project.
{% endhint %}

In the empty project that now has the Yarn Spinner for Unity package installed, right click in the Hierarchy and choose Yarn Spinner -> Dialogue Runner. This will add a new Dialogue System prefab to your scene, which we'll be working with in a moment.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 11.55.04 am.png" alt="" width="563"><figcaption><p>Creating a new Dialogue Runner in a scene.</p></figcaption></figure>

{% hint style="info" %}
Instead of right-clicking in the Hierarchy, you can also use the GameObject menu -> Yarn Spinner -> Dialogue Runner.
{% endhint %}

The Dialogue Runner that has been added to your scene is a prefab supplied by Yarn Spinner for Unity that acts as a bridge between the dialogue written in your Yarn scripts, and everything that happens in Unity.

Specifically, it works with two different things, which are key concepts when working with Yarn Spinner for Unity:

* a Yarn Project
* a Dialogue View

### Creating a Yarn Project

First, we'll look at the Yarn Project. A Yarn Project is a Untiy asset that lives on disk. Create one by right-clicking in the Assets pane and choose Create -> Yarn Spinner -> Yarn Project.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 12.03.20 pm.png" alt=""><figcaption><p>Creating a Yarn Project in your project's assets.</p></figcaption></figure>

With the new Yarn Project created, name it `FirstProject`, and then use the same menu to create a Yarn Script. Name the Yarn Script `MyStory`.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 12.06.06 pm.png" alt="" width="495"><figcaption><p>A Yarn Project and a Yarn Script in your prokect's assets.</p></figcaption></figure>

The Yarn Script you've created is actually a `.yarn` file that's now named `MyStory.yarn`. Double click it in the Assets pane to open it in Visual Studio Code.&#x20;

Put the following Yarn script into `MyStory.yarn`, save the file and return to Unity:

<details>

<summary>MyStory.yarn</summary>

```
title: Start
tags:
---
Narrator: Oh, hello!
    -> Hi, where am I?
        Narrator: You're in Unity!
            -> Oh.
            <<jump Oh>>
            -> How did I get here?
            <<jump Unity>>
===

title: Oh
---
Narrator: Yeah, fun, right?
===

title: Unity
---
Narrator: Someone read the Beginner's Guide!
===
```

</details>

To connect the Yarn Project you created to the Dialogue Runner that's in the scene, select the Dialogue Runner in the Hierarchy and drag the `FirstProject` from the Assets pane into the Yarn Project slot, as shown here:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 12.11.18 pm.png" alt="" width="563"><figcaption><p>The Inspector for the Dialogue System, showing the Yarn Project asset you created in the Yarn Project slot of the Dialogue Runner.</p></figcaption></figure>

With that done, select the Yarn Project `FirstProject` in the Assets pane, and look to the Inspector.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 2.05.15 pm.png" alt="" width="563"><figcaption></figcaption></figure>

You'll see the Source Files field contains `**/*.yarn` — this tells this specific Yarn Project to look for all `.yarn` files in the same folder as the Yarn Project asset, and any subfolders. Thus, any `.yarn` files next to it will be included as part of the project, which means `MyStory.yarn` will be found.

At this point, you can play your project, and step through the dialogue in the default Yarn Spinner for Unity Line View and Options List View:

<figure><img src="../../.gitbook/assets/beginnersguide.gif" alt=""><figcaption></figcaption></figure>

### What's a Line View and an Options List View?

To understand how this is working, it's important to understand the concept of Yarn Spinner Dialogue Views. Select the Dialogue System in the Hierarchy, and expand the Dialogue Views section:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 2.17.53 pm.png" alt="" width="563"><figcaption></figcaption></figure>

This section is where you specify which DIalogue Views should be used to display the content coming from the Yarn script(s): in other words, how the lines of dialogue, and choices, should be displayed.

A Dialogue Runner can have multiple Dialogue Views. For example, by default the Dialogue System prefab has one Dialogue View that's designed to display lines of dialogue (Line View), and another that's in charge of displaying options to the player (Options List View).

All Dialogue Views receive all lines and options, and it's up to them to handle them appropriately. So the Line View that we supply will only displays lines that are not options, and the Options List View will only display lines that are options.

{% hint style="info" %}
While Yarn Spinner for Unity supplies some basic Dialogue Views, you can also create your own. To learn about this visit [Creating Custom Dialogue Views](../../using-yarnspinner-with-unity/components/dialogue-view/custom-dialogue-views.md), but do note that it is a **significant** step from this Beginner's Guide.
{% endhint %}

## Next steps with Yarn Spinner for Unity

With that, we've reached the end of our beginner's guide. You're ready go forth and build games with Yarn Spinner! You're also equipped to work with the rest of the documentations here! Don't forget to [join the Discord](https://discord.com/invite/yarnspinner), to chat with other Yarn Spinner users, the Yarn Spinner team, seek help, and share your work.
