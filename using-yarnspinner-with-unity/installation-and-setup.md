---
description: >-
  This tutorial shows you how to install Yarn Spinner for Unity, the Unity
  integration for running Yarn and Yarn Spinner scripts in your Unity-based
  games.
---

# 📦 Installation

There are two ways to install Yarn Spinner for Unity: via the Package Manager, and via a `.unitypackage` file.

{% hint style="info" %}
We recommend installing it via the Package Manager, because it's easier to update to new versions of Yarn Spinner as they become available, it doesn't get embedded in the source code of your game, and you have more control over what gets added to your project.
{% endhint %}

## Install via the Unity Package Manager \(recommended\)

You can install the Yarn Spinner package into your project using the Package Manager window in Unity.

Yarn Spinner is available via the [OpenUPM registry](https://openupm.com). This is the simplest way to install Yarn Spinner, and makes it easy to keep it up to date.

{% hint style="info" %}
In order to follow the instructions in this section, your project needs to be using Unity 2020.1 or higher. If your project is using an earlier version of Unity, we recommend installing Yarn Spinner from Git.
{% endhint %}

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

![](../.gitbook/assets/installing-unity-package-manager-registry.png)

You can now install Yarn Spinner itself.

### Installing the Yarn Spinner package

1. Open the Window menu, and choose Package Manager.
2. In the toolbar, click Packages: In Project, and choose My Registries.

![](../.gitbook/assets/installing-unity-package-manager-select-package-list.png)

1. Yarn Spinner will appear in the list. Select it, and click Install.

![](../.gitbook/assets/installing-unity-package-manager-registry-select-package.png)

Yarn Spinner will download and install into your project.

You can verify that everything is imported succesfully by looking for Yarn Spinner under Packages, in the Project pane.

![Verify that Unity has the package by checking the Packages folder of the Project pane.](../.gitbook/assets/screen-shot-2021-03-07-at-2.16.14-pm.png)

## Install from GitHub

As an alternative to downloading Yarn Spinner from OpenUPM, you can install Yarn Spinner by downloading the package directly from GitHub, where the project's source code is stored.

{% hint style="info" %}
Where possible, we recommend installing Yarn Spinner from OpenUPM rather than GitHub, because it's easier to update to new versions.
{% endhint %}

To install Yarn Spinner from GitHub, follow these instructions.

#### Unity 2019.3 and later

If you're using Unity 2019.3 or later, you can install the package from GitHub via the Package Manager window:

1. In Unity, open the Window menu, and choose Package Manager.
2. Click the `+` button, and choose "Add package from git URL".

![](../.gitbook/assets/installing-unity-git-select-url.png)

1. In the text field that appears, enter the following URL: **`https://github.com/YarnSpinnerTool/YarnSpinner-Unity.git`**.

{% hint style="info" %}
Be sure to type the URL exactly as it appears in this document, or the installation won't work.
{% endhint %}

1. The project will download and install. This might take a moment.

#### Unity 2018.4 to Unity 2019.2

If you're using an earlier version of Unity, you'll need to add the package by updating your project's manifest file:

* Go to the folder that your project is in.
* Open the `Packages` folder.
* Open the file `manifest.json` in your text editor \(for example, Visual Studio Code.\)
* Update the file to include Yarn Spinner's GitHub URL \(don't forget the comma at the end!\):

\`\`\`json { "dependencies": { "dev.yarnspinner.unity": "[https://github.com/YarnSpinnerTool/YarnSpinner-Unity.git](https://github.com/YarnSpinnerTool/YarnSpinner-Unity.git)", "com.unity.2d.sprite": "1.0.0", ...

\`\`\`

* Return to Unity, and Yarn Spinner will download and install.

## Install as a file

If you don't want to install Yarn Spinner as a package, you can download it as a `.unitypackage` file, and extract it into your project.

{% hint style="info" %}
This approach works in all versions of Unity. However, because it installs the Yarn Spinner files directly into your project's Assets folder and doesn't do any versioning, updating to a newer version of Yarn Spinner is more complicated. Where possible, we recommend installing Yarn Spinner from OpenUPM or from Git.
{% endhint %}

To download and install the file, follow these steps:

1. In Unity, open the Window menu, and choose Package Manager.
2. Locate **Text Mesh Pro** in the list, and select it. 
3. Click the Install button to install Text Mesh Pro. This package is required for Yarn Spinner to work.
4. Next, open your browser, and go to the [most recent release](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/releases/latest) of Yarn Spinner for Unity on GitHub.
5. Download the `.unitypackage` for that release.

![The release page on GitHub.](../.gitbook/assets/installing-unity-from-file-releases-page-1.0.png)

1. Open the `.unitypackage`. Unity will ask which files you want to add. In almost every case, you'll want to import all files.

![Importing the package.](../.gitbook/assets/installing-unity-from-file-package-import-1.0.png)

1. Click Import.

## Next Steps

Once you've installed Yarn Spinner, you're ready to start using it!

