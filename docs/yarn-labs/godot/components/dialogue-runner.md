---
description: >-
  Learn about the Dialogue Runner, which runs the contents of your Yarn Scripts
  and delivers lines, options and commands to your game.
---

# Dialogue Runner

The Dialogue Runner is the bridge between the dialogue that you've written in your Yarn scripts and the other components of your game. It's a component that's responsible for loading, running and managing the contents of a [Yarn Project](../importing-yarn-files/yarn-projects.md), and for delivering the content of your [Yarn scripts](../importing-yarn-files/yarn-scripts.md) to the other parts of your game, such as your user interface.

Setting up a Dialogue Runner is the first step in adding dialogue to your game. To use a Dialogue Runner, you add the DialogueRunner script to a node in your scene, connect it to [Dialogue Views](dialogue-views/), and provide it with a [Yarn Project](../importing-yarn-files/yarn-projects.md) to run.

When you want to start running the dialogue in your game, you call the Dialogue Runner's StartDialogue method. When you do this, the Dialogue Runner will begin delivering lines, options and commands to its Dialogue Views.

The Dialogue Runner is designed to work with other components of Yarn Spinner for Godot:

* The contents of your dialogue are delivered to your [Dialogue Views](dialogue-views/).
* The values of [variables](../../../getting-started/writing-in-yarn/logic-and-variables.md) are stored and retrieved using the Dialogue Runner's [Variable Storage](../../../yarn-spinner-for-game-engines/unity/components/variable-storage/).
* The content that users should see - that is, the text in their current language, voice over clips, and other assets - are retrieved using the Dialogue Runner's [Line Provider](line-provider/).

{% hint style="info" %}
The bare-bones minimum that a Dialogue Runner needs in order to work is a Yarn Project and at least one Dialogue View. If you don't set up a Variable Storage or a Line Provider, the Dialogue Runner will use temporary placeholders.
{% endhint %}

### Inspector

| Property                      | Description                                                                                                                                                                                                                                                                                                                                                                                                  |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Yarn Project                  | The [Yarn Project](../importing-yarn-files/yarn-projects.md) that this Dialogue Runner is running.                                                                                                                                                                                                                                                                                                           |
| Variable Storage              | The [Variable Storage](../../../yarn-spinner-for-game-engines/unity/components/variable-storage/) to store and retrieve variable data from. If you do not set this, the Dialogue Runner will create an [In Memory Variable Storage](variable-storage/in-memory-variable-storage.md) for you at runtime.                                                                                                      |
| Line Provider                 | The [Line Provider](line-provider/) to use to get user-facing content for each line. If you do not set this, the Dialogue Runner will create a [Text Line Provider](line-provider/text-line-provider.md) for you at runtime.                                                                                                                                                                                 |
| Dialogue Views                | The [Dialogue Views](dialogue-views/) to send lines, options and commands to. Add nodes that have scripts implementing the DialogueViewBase interface to this list in order for them to handle your dialogue lines and options. If a node that is added to this list does not implement DialogueViewBase, it will not function as a view, and an error explaining this will be logged to the output console. |
| Start Automatically           | If this is turned on, the Dialogue Runner will start running the node named Start Node when the scene starts. If this is not turned on, you will need to call StartDialogue to start running.                                                                                                                                                                                                                |
| Start Node                    | If Start Automatically is turned on, the Dialogue Runner will start running this node when the scene starts. (If your Yarn Project does not contain a node with this name, an error will be reported.)                                                                                                                                                                                                       |
| Run Selected Options as Lines | If this is turned on, when the user chooses an option, the Dialogue Runner will run the selected option as if it were a Line.                                                                                                                                                                                                                                                                                |
| Verbose Logging               | If this is turned on, the Dialogue Runner will log information about the state of each line to the Console as it's run.                                                                                                                                                                                                                                                                                      |

### Signals

| Signal             | Description                                                                                                                                                                                                               |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| onNodeStart        | A signal that's emitted when the Dialogue Runner begins running a new node. This may be fired multiple times during a dialogue run.                                                                                       |
| onNodeComplete     | A signal that's emitted when the Dialogue Runner reaches the end of a node. This may be fired multiple times during a dialogue run.                                                                                       |
| onDialogueComplete | A signal that's emitted when the Dialogue Runner stops running dialogue.                                                                                                                                                  |
| onCommand          | A signal that's emitted when a Command is encountered. This will only be called if no other part of the system has already handled the command, such as command handlers registered via YarnCommand or AddCommandHandler. |
