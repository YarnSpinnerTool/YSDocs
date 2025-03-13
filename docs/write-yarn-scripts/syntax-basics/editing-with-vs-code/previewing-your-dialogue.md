---
description: >-
  Preview your dialogue within the Yarn Spinner for Visual Studio Code
  Extension.
icon: play
---

# Previewing Your Dialogue

You can run your Yarn script inside the Visual Studio Code extension, without having to import it into a game. This means that you can write content for your game even if the game isn't yet ready to have dialogue added to it. It's also useful for quickly checking to see if your Yarn script works the way that you want it to before testing it in your game.

{% hint style="info" %}
This is fundamentally the same preview experience you'll get if you Test your dialogue at [https://try.yarnspinner.dev ](https://try.yarnspinner.dev)&#x20;
{% endhint %}

![Previewing dialogue in Visual Studio Code. On the left hand side, Yarn script is being edited, and on the right hand side, the same script is being played through.](../../../.gitbook/assets/vscode-preview.png)

## Showing the Dialogue Preview

To preview your dialogue in Visual Studio Code, open the Command Palette by pressing `Command-Shift-P` (`Control-Shift-P` on Windows), and type "Preview Dialogue". Your current Yarn project will open to the side, and you can begin playing through your script.

{% hint style="info" %}
By default, the dialogue preview will begin playing from the node named "Start". If no node named "Start" exists, then the dialogue preview will begin playing from the first node in one of your files. You can choose which node to start playing from in the menu at the top-right of the preview area.
{% endhint %}

## Preview Features

While playing through your dialogue in preview mode, there are several features that can be useful to test out a script.

* **Changing the starting node:** By default, the dialogue preview will start playing from a node named "Start", if one is present in your Yarn files. If you want to play from a different node, open the list of nodes and choose the node you want to start from.
* **Changing whether lines are shown one at a time, or all at once:** By default, the dialogue preview shows each line and command one and a time. You can change this to delivering everything all at once by opening the Settings menu and changing the setting to "Show Lines All At Once".
* **Showing the contents of variables:** You can see the current contents of all [variables](../logic-and-variables.md) in your script by opening the Settings menu and choosing "Show Variables". A list of variables will appear, and as you play through your script, they'll update when your script changes their contents.
* **Changing whether 'unavailable' lines are shown:** Options can be [marked as 'unavailable'](../flow-control.md#conditional-options) depending on whether or not a test has passed. By default, options that fail this test are not shown in the dialogue preview at all; to change this to showing all options (including ones that the user can't choose), open the Settings menu and choose "Show Unavailable Options".
* **Restarting the script:** When you click the Restart button, the dialogue preview will restart from the currently selected starting node.

## Exporting Your Script

You can export a stand-alone HTML file containing a runnable version of your Yarn script, which you can send to other people for them to play. This can be particularly useful for writers who want to get feedback on their scripts before working with other team members to integrate their content.

To export your script, click the Export button, and choose where to save the file. The file can then be sent anywhere you like, and can be opened in all major web browsers.
