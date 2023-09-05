---
description: >-
  Learn about Yarn Projects, which group your scripts together for use in a
  Dialogue Runner.
---

# Yarn Projects

A Yarn Project is a file that links multiple [Yarn scripts](yarn-scripts.md) together. Yarn projects are how Dialogue Runners work with your content.

{% hint style="info" %}
If you are upgrading your version of Yarn Spinner from version 2.2 or earlier, you will need to upgrade your Yarn Project. See [Upgrading Yarn Projects](#upgrading-yarn-projects) to learn how to do this.
{% endhint %}

![The Yarn Project inspector. The configurable properties of the Yarn Project are visible at the top, and the information about the imported project is visible at the bottom.](../../.gitbook/assets/yarn-project-inspector.png)

## Creating a New Yarn Project

To create a new Yarn Project, follow these steps:

* Open the Assets menu, and choose Yarn Spinner -> Yarn Project.
* Unity will create a new file. Type in a name for the file, and press return.

![Creating a new Yarn project.](../../.gitbook/assets/yarn-spinner-unity-creating-yarn-project.png)

## Adding Yarn scripts to a Yarn Project

On their own, a Yarn Project doesn't do anything. In order to be useful, you need to add Yarn scripts to it.

Yarn Projects include all Yarn Scripts that the project finds in the Source Files directory. By default, that means all Yarn Scripts in the same directory as the Yarn Project, and all of that directory's children.

When you add a Yarn Script to the same folder as a Yarn Project, it will automatically be included in the Yarn Project. When you make changes to the script, the Yarn Project will automatically be re-imported.

You can change the locations that a Yarn Project looks for Yarn Scripts by modifying the Source Files setting. Each entry in the Source Files setting is a _search pattern_.

|Pattern|Description|Examples|
|---|---|---|
|`*`| any filename| "`*.yarn`" will find "One.yarn" and "Two.yarn".|
|`**/*`| any path, including subdirectories| "`**/*.yarn`" will find "One.yarn" and "Subfolder/Two.yarn".|
|..| the parent folder| "`../*.yarn`" will find "One.yarn" in the parent folder.|

You can add as many entries to the Source Files field as you like. If a file is matched by multiple patterns, it will only be included once.

![An example of a custom Source Files setting. In this example, the Yarn Project will use all `.yarn` files in the same folder and its sub-folders, as well as the file `Common.yarn` in the folder above it.](../../.gitbook/assets/yarn-project-custom-source-files.png)

A Yarn script can be included in more than one Yarn Project.

### Creating a Project from a Script

You can create a new Yarn Project from a script. To do this, follow these steps:

* Select the Yarn script in the Project pane.
* In the Inspector, click the Create New Yarn Project button.

![The 'Create New Yarn Project' button in the Inspector.](../../.gitbook/assets/yarn-spinner-unity-create-new-project-button.png)

* Clicking this button does two things:
  * A new Yarn Project will be created next to the Yarn script.
  * The new Yarn Project will include the Yarn script you created it from in its list of source scripts.

## Managing Variables

A Yarn Project's inspector shows information about every [variable](../../getting-started/writing-in-yarn/logic-and-variables.md) that are used in the Yarn scripts. This section of the Inspector shows the name, type, description, and default value of each variable.

The Inspector will show information about every variable in the project. If you use a `declare` statement to declare a variable, you can control the initial value of a variable, as well as its description. If you don't declare a variable, Yarn Spinner will attempt to figure the variable's type out based on how it's used, and won't be able to provide a description.

![The list of variables in a Yarn Project.](../../.gitbook/assets/yarn-project-variables.png)

## Managing Localisations and Assets

When you write a Yarn script, you write it in a specific human language. This is referred to as the 'base' language of the script. It's called the base language because it's the one you start with, and the one you translate into other languages. 

{% hint style="info" %}
Unless you change it to something else, Yarn Spinner will set the base language to your computer's current locale.
{% endhint %}

You can set the base language of a Yarn Project in the Inspector by changing the Base Language setting.

![Updating the base language of a Yarn Project](../../.gitbook/assets/default-language.png)

If you want to translate your scripts into another language, or if you want to associate each line with assets (like voice over audio clips), you create a new Localisation. To learn about this process, see [Adding Localizations and Assets to Projects](../assets-and-localization/README.md).

## Using Yarn Projects with Dialogue Runners

Yarn Projects are used by Dialogue Runners. When a Dialogue Runner is told to start running dialogue, it reads it from the Yarn Project it's been provided.

{% hint style="info" %}
If you try to start a Dialogue Runner and it doesn't have a Yarn Project, or the Yarn Project doesn't have any Yarn scripts, or if any of the Yarn scripts contain an error, the Dialogue Runner won't be able to run.
{% endhint %}

## Inspector

|Property|Description|
|---|---|
|Source Scripts|The list of places that this Yarn Project looks for Yarn Scripts.|
|Base Language|The language that the Yarn Scripts are written in.|
|Localisations|<p>A mapping of languages to string tables and associated assets.</p><p>This list will only appear if the project is not using the Unity Localisation system. See [Adding Localizations and Assets to Projects](../assets-and-localization/README.md) for more information.</p>|
|Use Addressable Assets|<p>If this is turned on, the Yarn Project will be set up to tell other parts of the game that localised assets like audio files should be fetched using the [Addressable Assets](https://docs.unity3d.com/Packages/com.unity.addressables@latest/index.html) system.</p> <p>This checkbox will only appear if the Addressable Assets package is installed in your project, and if the project is not using the Unity Localisation System.</p>|
|Use Unity Localisation System|<p>If this is turned on, the Yarn Project will use the Unity Localisation System to store line data in.</p><p>This checkbox will only appear if the Localisation package is installed in your project.</p>|
|Unity Localisation String Table|<p>The String Table Collection that the Yarn Project uses. When the project is imported or reimported, this String Table will be filled with line content that comes from the project's Yarn Scripts.</p><p>This field will only appear if project is using the Unity Localisation system.</p>|
|Export Strings as CSV|When you click this button, all of the lines in the Yarn Scripts that this project uses will be written to a `.csv` file, which can be translated to other languages. See [Adding Localizations and Assets to Projects](../assets-and-localization/README.md) for more information.|
|Update Existing Strings Files|<p>When you click this button, all `.csv` strings files that are configured in the Languages to Source Assets list will be updated with any lines that have been added, modified or deleted since the strings file was created.</p><p> This checkbox will only appear if the project is not usin the Unity Localisation system. See [Adding Localizations and Assets to Projects](../assets-and-localization/README.md) for more information.</p>|
|Add Line Tags to Scripts|When you click this button, any line of dialogue in the Source Scripts list that doesn't have a `#line:` tag will have one added. See [Adding Localizations and Assets to Projects](../assets-and-localization/README.md) for more information.|

## Upgrading Yarn Projects

If you are upgrading your version of Yarn Spinner from version 2.2 or earlier, you will need to upgrade your Yarn Project. To do this, select the Yarn Project, and click Upgrade Yarn Project.

After upgrading your Yarn Project, you will need to set up any localisations you had previously configured on your project. Follow the instructions in [Built-In Localisation System](../assets-and-localization/inbuilt-localisation.md) or [Unity Localisation](../assets-and-localization/unity-localization.md), depending on what your game is using.

You will also need to either move all of your Yarn Scripts into the same folder as the Yarn Project, or update the Yarn Project's Source Files setting to tell the Yarn Project where to find your scripts.

![Upgrading an old-style Yarn Project from Yarn Spinner 2.2 or earlier](../../.gitbook/assets/yarn-project-upgrade.png)

Watch a video where Yarn Spinner developer Jon Manning walks you through upgrading a Yarn Project:

{% embed url="https://www.youtube.com/watch?v=PQ24SOxytts" %}