---
description: >-
  This page shows you how to install Yarn Spinner for Godot, the Godot
  integration for running Yarn and Yarn Spinner scripts in your Godot-based
  games.
---

# 📦 Installation for Godot

{% hint style="danger" %}
Yarn Spinner for Godot is a Yarn Labs project. It is not fully, or officially supported, and may break, or change at any time.
{% endhint %}

## 📦 Installation for Godot

Download a[ copy of the latest version of Yarn Spinner for Godot](https://github.com/YarnSpinnerTool/YarnSpinner-Godot/releases) from the [GitHub repository](https://github.com/YarnSpinnerTool/YarnSpinner-Godot/), or clone the repository somewhere.

Locate the `addons/` directory in your new local copy of Yarn Spinner for Godot:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 3.01.50 pm.png" alt="" width="563"><figcaption><p>The <code>addons</code> directory in a local copy of Yarn Spinner for Godot.</p></figcaption></figure>

Put a copy of this directory into your new Godot project, either by dragging the folder in your file manager (e.g. Finder or Explorer) into the folder of the Godot project, or by dragging from your file manager into the FileSystem dock of your Godot project:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 3.04.04 pm.png" alt="" width="408"><figcaption><p>The FileSystem dock in Godot, after dragging the <code>addons</code> directory in.</p></figcaption></figure>

Next, choose the Project menu -> Tools -> C# -> Create C# solution. This will create a C# project for you. We have to do this to trigger the creation of the `.csproj` file, which is necessary to let Godot know about the Yarn Spinner plugin.

Next, open the project folder in Visual Studio Code. In the sidebar of VS Code, the `.csproj` file and add the following line to it, inside the `<Project>` `</Project>` tags, but not inside an `<ItemGroup>` or `<PropertyGroup>:`

```
  <Import Project="addons\YarnSpinner-Godot\YarnSpinner-Godot.props" />
```

Your brand new project should look something like this in VSCode:

<figure><img src="../../../.gitbook/assets/YarnSpinnerGodot-Csproj-File.png" alt=""><figcaption><p>The <code>.csproj</code> for your project.</p></figcaption></figure>

Save the tweaked `.csproj` file and return to Godot, everything is almost ready to go. Click the Build button in the very top right-hand corner of the Godot window. This will trigger a build of the C# solution for the project, which is required to make Godot aware of Yarn Spinner for Godot.

Once the build is complete, open the Project menu -> Project Settings, change to the Plugins tab, and tick the enabled box next to the Yarn Spinner for Godot plugin:

<figure><img src="../../../.gitbook/assets/Screenshot%202023-10-18%20at%2010.40.42%E2%80%AFam.png" alt="" width="563"><figcaption><p>The Project Settings, showing the Plugins tab.</p></figcaption></figure>

With that, you're ready to go!
