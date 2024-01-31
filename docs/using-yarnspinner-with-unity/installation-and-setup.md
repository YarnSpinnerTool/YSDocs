---
description: >-
  This page shows you how to install Yarn Spinner for Unity, the Unity
  integration for running Yarn and Yarn Spinner scripts in your Unity-based
  games.
---

# 📦 Installation for Unity

You can download and install Yarn Spinner for Unity in four different ways:

* [buy Yarn Spinner for Unity from our Itch.io store](https://yarnspinnertool.itch.io/yarn-spinner), download it, and add the package to your project from the `.unitypackage`
* [buy Yarn Spinner from the Unity Asset Store](https://assetstore.unity.com/packages/tools/behavior-ai/yarn-spinner-for-unity-267061), download it, and install it via Unity
* install Yarn Spinner for Unity via the Unity Package Manager
* install Yarn Spinner for Unity from GitHub

{% hint style="info" %}
Yarn Spinner is an open source project. You can directly support the Yarn Spinner Team by purchasing Yarn Spinner from [Itch](https://yarnspinner.itch.io) or the [Unity Asset Store](https://assetstore.unity.com/packages/tools/behavior-ai/yarn-spinner-for-unity-267061), but it will always also be available for free. To support the continued development of Yarn Spinner, purchasing Yarn Spinner for Unity from one of the storefronts. This is the best way to directly support the Yarn Spinner team.
{% endhint %}

## Install from Itch.io

First, visit the [Yarn Spinner Itch.io Store](https://yarnspinnertool.itch.io/yarn-spinner), and click the Buy Now button, and complete the checkout process.&#x20;

Once you've purchased Yarn Spinner, you'll find a Download button at the top of the page:

<figure><img src="../.gitbook/assets/PNG image.jpeg" alt=""><figcaption></figcaption></figure>

The download button will take you the following page, where you can download the Yarn Spinner for Unity `.unitypackage`:

<figure><img src="../.gitbook/assets/PNG image (1).jpeg" alt=""><figcaption></figcaption></figure>

Once you've downloaded the `.unitypackage`, with the Unity project you want to use it in open and ready to go, double click it. Unity will then allow you to import the package into your project:

<figure><img src="../.gitbook/assets/Screenshot 2023-11-29 at 4.03.41 pm.png" alt="" width="375"><figcaption></figcaption></figure>

## Install from the Unity Asset Store

First, [visit the Unity Asset Store page for Yarn Spinner for Unity](https://assetstore.unity.com/packages/tools/behavior-ai/yarn-spinner-for-unity-267061), and add it to your cart, and complete your purchase while logged into the same Unity account you use to activate Unity.

<figure><img src="../.gitbook/assets/Screenshot 2024-01-31 at 3.48.43 pm.png" alt=""><figcaption></figcaption></figure>

Once you've purchased Yarn Spinner for Unity, you'll find the Add to Cart button replaced by an Open in Unity button. Click this button to launch Unity, and the Package Manager will locate your purchased package:

<figure><img src="../.gitbook/assets/Screenshot 2024-01-31 at 3.41.36 pm.png" alt="" width="375"><figcaption></figcaption></figure>

Once the Package Manager has located the package, you can use the Download button to fetch it:

<figure><img src="../.gitbook/assets/Screenshot 2024-01-31 at 3.42.04 pm.png" alt=""><figcaption></figcaption></figure>

Once Yarn Spinner for Unity has downloaded, you can use the Import button to start the process of adding it to your project:

<figure><img src="../.gitbook/assets/Screenshot 2024-01-31 at 3.43.55 pm.png" alt=""><figcaption></figcaption></figure>

This will trigger the Import Unity Package workflow, where you can use the Import button to add the Yarn Spinner for Unity package to your project:

<figure><img src="../.gitbook/assets/Screenshot 2024-01-31 at 3.46.55 pm.png" alt="" width="375"><figcaption></figcaption></figure>

And with that, you're ready to use Yarn Spinner! You might also want to download and import the Yarn Spinner for Unity Samples as a `.unitypackage`, from here.

{% hint style="info" %}
You can review [Unity's documentation for using the Asset Store](https://docs.unity3d.com/Manual/AssetStorePackages.html) for further guidance on working with purchased packages.
{% endhint %}

## Installing from other sources

If you would prefer to download and install Yarn Spinner for Unity outside of Itch or the Unity Asset Store, we provide the following methods:

<details>

<summary>Install via the Unity Package Manager</summary>

## Install via the Unity Package Manager

You can also install the Yarn Spinner package into your project using the Package Manager window in Unity. Specifically, Yarn Spinner is available via the [OpenUPM registry](https://openupm.com).&#x20;

In order to follow the instructions in this section, your project needs to be using Unity 2020.1 or higher. If your project is using an earlier version of Unity, we recommend installing Yarn Spinner from Git.

### Setting Up the OpenUPM Registry in Your Project

Before you can install Yarn Spinner from OpenUPM, you first need to configure your project so that it knows where to get the package from.

1. In Unity, open the Edit menu, and choose Project Settings.
2. In the list of sections at the left hand side of the window, select Package Manager.

This window is where you tell Unity about where to find packages that come from registries besides Unity's built-in one.

1. In the Name field, type `OpenUPM`.
2. In the URL field, type `https://package.openupm.com`.
3. In the Scopes field, type `dev.yarnspinner`.
4. Click Save.

When you're done, the settings window should look like this:

<img src="../../.gitbook/assets/installing-unity-package-manager-registry.png" alt="" data-size="original">

You can now install Yarn Spinner itself.

### Installing the Yarn Spinner package

1. Open the Window menu, and choose Package Manager.
2. In the toolbar, click Packages: In Project, and choose My Registries.

<img src="../../.gitbook/assets/installing-unity-package-manager-select-package-list.png" alt="" data-size="original">

1. Yarn Spinner will appear in the list. Select it, and click Install.

<img src="../../.gitbook/assets/installing-unity-package-manager-registry-select-package.png" alt="" data-size="original">

Yarn Spinner will download and install into your project.

You can verify that everything is imported succesfully by looking for Yarn Spinner under Packages, in the Project pane.

<img src="../../.gitbook/assets/Screen Shot 2021-03-07 at 2.16.14 pm.png" alt="Verify that Unity has the package by checking the Packages folder of the Project pane." data-size="original">

</details>

<details>

<summary>Install from GitHub</summary>

## Install from GitHub

As an alternative to downloading Yarn Spinner from OpenUPM, you can install Yarn Spinner by downloading the package directly from GitHub, where the project's source code is stored.

Where possible, we recommend installing Yarn Spinner via a purchased `.unitypackage`, or from OpenUPM rather than GitHub, because it's easier to update to new versions.

To install Yarn Spinner from GitHub, follow these instructions.

1. Make sure your system [has Git (minimum version 2.14.0) installed](https://git-scm.com/).
2. In Unity, open the Window menu, and choose Package Manager.
3. Click the `+` button, and choose "Add package from git URL".
4. In the text field that appears, enter the following URL: \
   **`https://github.com/YarnSpinnerTool/YarnSpinner-Unity.git#current`**\
   Be sure to type the URL exactly as it appears in this document.
5. The project will download and install. This might take a moment.

</details>

## Next Steps

Once you've installed Yarn Spinner, you're ready to start using it!
