---
description: Quick Start Guide
---

# Quick Start

After following the instructions to [install the plugin](installation-and-setup.md), in your Godot project, click the Instantiate Child Scene button:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 3.33.38 pm.png" alt="" width="563"><figcaption><p>The chain-link button, for instantiating a child scene.</p></figcaption></figure>

And navigate into the `addons/YarnSpinner-Godot/Scenes` folder of your project, and choose the `DefaultDialogueSystem.tscn` file as the scene to instantiate:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 3.34.26 pm.png" alt="" width="563"><figcaption><p>Choosing the provided <code>DefaultDialogueSystem.tscn</code>.</p></figcaption></figure>

Then, right click the new scene in the Scene dock, and check the "Editable Children" option. This will allow you to view all of the components that make up the default dialogue system, and set options on them in the inspector dock.

Your Scene dock will look like this showing a node hierarchy that's entirely based on the `DefaultDialogueSystem.tscn` scene that you instantiated:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 10.30.49 am.png" alt="" width="405"><figcaption><p>The <code>DefaultDialogueSystem</code> instantiated into your scene.</p></figcaption></figure>

{% hint style="info" %}
You could also instantiate the `DefaultDialogueSystem.tscn` into your scene at a lower part of the hierarchy, instead of the root node, to display dialogue using the provided default UI, instead.
{% endhint %}

Next, create a new Yarn Project using the menu Tools > YarnSpinner >Create Yarn Project:

<figure><img src="../../.gitbook/assets/YarnSpinnerGodot-Create-YarnProject.png" alt="" width="563"><figcaption><p>Opening the menu to create a new .yarnproject file.</p></figcaption></figure>

Then choose a directory to save your new YarnProject in. For example, you can save it to the root of your project. Name the new Yarn Project `FirstProject.yarnproject`:

<figure><img src="../../.gitbook/assets/YarnSpinnerGodot-Create-YarnProject-Dialog.png" alt="" width="563"><figcaption><p>Selecting a location to save your .yarnproject file.</p></figcaption></figure>

Next, create a new Yarn script (a file with a `.yarn` extension) by using the menu Tools > YarnSpinner >Create Yarn Script. In the resulting "Create a new Yarn Script" window, set the File name to `MyStory.yarn`, and click the Save button::

<figure><img src="../../.gitbook/assets/YarnSpinnerGodot-Create-YarnScript.png" alt="" width="413"><figcaption><p>Opening the Create Yarn Script window</p></figcaption></figure>

It may take a moment, but Godot will import your new `.yarn` file, and it will appear in the FileSystem dock. When it's appeared, double-click on the Yarn Project, `FirstProject.yarnproject` in the FileSystem dock and look to the Inspector, making sure that `res://MyStory.yarn` is in the list of Source Scripts, which are the Yarn scripts that compromise the new project:

<figure><img src="../../.gitbook/assets/YarnSpinnerGodot-YarnProject-Inspector.png" alt="" width="563"><figcaption><p>The Yarn Project, with the Yarn script identified as a Source Script.</p></figcaption></figure>

Next, open the `MyStory.yarn` file in VS Code, and add the following Yarn script to it, before saving it and returning to Godot:

<details>

<summary>MyStory.yarn</summary>

```
title: Start
tags:
---
Narrator: Oh, hello!
    -> Hi, where am I?
        Narrator: You're in Godot!
            -> Oh.
                <<jump Oh>>
            -> How did I get here?
                <<jump Godot>>
===

title: Oh
---
Narrator: Yeah, fun, right?
===

title: Godot
---
Narrator: Someone read the Beginner's Guide!
===
```

</details>

Select the `DialogueRunner` node in the Scene dock, and look to the Inspector. Selecting "Editable Children" earlier in the guide is what will allow you to see the `DialogueRunner` node and edit its options. Assign the Yarn Project you created to the `DialogueRunner` by dragging the `FirstProject.tres` Yarn Project from the FileSystem dock into the Yarn Project slot of the Inspector:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 10.34.38 am.png" alt="" width="563"><figcaption><p>The new Yarn Project resource assigned as the Yarn Project for the <code>DialogueRunner</code>.</p></figcaption></figure>

Finally, enter `Start` as the Start Node, and tick the box next to Starts Automatically:

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-18 at 10.35.23 am.png" alt="" width="563"><figcaption><p>Setting the Start Node, and that we want this <code>DialogueRunner</code> to start automatically.</p></figcaption></figure>

Save your scene as `Demo.tscn`, and run the game. At this point, you can play your project, and step through the dialogue in the default Yarn Spinner for Godot Line Presenter and Options Presenter:

<figure><img src="../../.gitbook/assets/beginnersgodot.gif" alt="" width="563"><figcaption></figcaption></figure>

## Next steps with Yarn Spinner for Godot <a href="#next-steps-with-yarn-spinner-for-godot" id="next-steps-with-yarn-spinner-for-godot"></a>

With that, we've reached the end of our beginner's guide. You're ready go forth and build games with Yarn Spinner! You're also equipped to work with the rest of the documentations here! Don't forget to [join the Discord](https://discord.com/invite/yarnspinner) to chat with other Yarn Spinner users, the Yarn Spinner team, seek help, and share your work.
