---
description: >-
  Learn about the Dialogue Runner, which runs the contents of your Yarn Scripts
  and delivers lines, options and commands to your game.
---

# Dialogue Runner

The Dialogue Runner is the bridge between the dialogue that you've written in your Yarn scripts and the other components of your game. It's a component that's responsible for loading, running and managing the contents of a [Yarn Project](../importing-yarn-files/yarn-projects.md), and for delivering the content of your [Yarn scripts](../importing-yarn-files/yarn-scripts.md) to the other parts of your game, such as your user interface.&#x20;

Setting up a Dialogue Runner is the first step in adding dialogue to your game. To use a Dialogue Runner, you add it to a game object in your scene, connect it to [Dialogue Views](dialogue-view/), and provide it with a [Yarn Project](../importing-yarn-files/yarn-projects.md) to run.&#x20;

When you want to start running the dialogue in your game, you call the Dialogue Runner's [StartDialogue](../../api/csharp/yarn.unity/dialoguerunner/dialoguerunner.startdialogue-system.string.md) method. When you do this, the Dialogue Runner will begin delivering lines, options and commands to its Dialogue Views.

The Dialogue Runner is designed to work with other components of Yarn Spinner for Unity:

* The contents of your dialogue are delivered to your [Dialogue Views](dialogue-view/).
* The values of [variables](../../getting-started/writing-in-yarn/logic-and-variables.md) are stored and retrieved using the Dialogue Runner's [Variable Storage](variable-storage.md).
* The content that users should see - that is, the text in their current language, voice over clips, and other asset - are retrieved using the Dialogue Runner's [Line Provider](line-provider.md).

{% hint style="info" %}
The bare-bones minimum that a Dialogue Runner needs in order to work is a Yarn Project and at least one Dialogue View. If you don't set up a Variable Storage or a Line Provider, the Dialogue Runner will use temporary placeholders.
{% endhint %}

### Inspector

#### Yarn Project

