---
description: >-
  Learn about the Dialogue Runner, which runs the contents of your Yarn Scripts
  and delivers lines, options and commands to your game.
---

# Dialogue Runner

The Dialogue Runner is the bridge between the dialogue that you've written in your Yarn scripts and the other components of your game. It's a component that's responsible for loading, running and managing the contents of a [Yarn Project](../importing-yarn-files/yarn-projects.md), and for delivering the content of your [Yarn scripts](../importing-yarn-files/yarn-scripts.md) to the other parts of your game, such as your user interface.&#x20;

Setting up a Dialogue Runner is the first step in adding dialogue to your game. To use a Dialogue Runner, you add it to a game object in your scene, connect it to [Dialogue Views](dialogue-view/README.md), and provide it with a [Yarn Project](../importing-yarn-files/yarn-projects.md) to run.&#x20;

When you want to start running the dialogue in your game, you call the Dialogue Runner's [StartDialogue](../../api/csharp/yarn.unity/dialoguerunner/dialoguerunner.startdialogue-system.string.md) method. When you do this, the Dialogue Runner will begin delivering lines, options and commands to its Dialogue Views.

The Dialogue Runner is designed to work with other components of Yarn Spinner for Unity:

* The contents of your dialogue are delivered to your [Dialogue Views](dialogue-view/README.md).
* The values of [variables](../../getting-started/writing-in-yarn/logic-and-variables.md) are stored and retrieved using the Dialogue Runner's [Variable Storage](./variable-storage/README.md).
* The content that users should see - that is, the text in their current language, voice over clips, and other assets - are retrieved using the Dialogue Runner's [Line Provider](./line-provider/README.md).

{% hint style="info" %}
The bare-bones minimum that a Dialogue Runner needs in order to work is a Yarn Project and at least one Dialogue View. If you don't set up a Variable Storage or a Line Provider, the Dialogue Runner will use temporary placeholders.

If your game is using the [Unity Localization system](../assets-and-localization/unity-localization.md), your Dialogue Runner must use a [Unity Localised Line Provider](line-provider/unity-localised-line-provider.md).
{% endhint %}

### Inspector

| Property                      | Description                                                                                                                                                                                                                                                                                                                                                                                     |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Yarn Project                  | The [Yarn Project](../importing-yarn-files/yarn-projects.md) that this Dialogue Runner is running.                                                                                                                                                                                                                                                                                              |
| Variable Storage              | The [Variable Storage](variable-storage/README.md) to store and retrieve variable data from. If you do not set this, the Dialogue Runner will create an [In Memory Variable Storage](variable-storage/in-memory-variable-storage.md) for you at runtime.                                                                                                                                         |
| Line Provider                 | The [Line Provider](line-provider/README.md) to use to get user-facing content for each line. If you do not set this, the Dialogue Runner will create a [Text Line Provider](line-provider/text-line-provider.md) for you at runtime.                                                                                                                                                        |
| Dialogue Views                | The [Dialogue Views](dialogue-view/README.md) to send lines, options and commands to.                                                                                                                                                                                                                                                                                                                    |
| Start Automatically           | If this is turned on, the Dialogue Runner will start running the node named Start Node when the scene starts. If this is not turned on, you will need to call [StartDialogue](../../api/csharp/yarn.unity/dialoguerunner/dialoguerunner.startdialogue-system.string.md) to start running.                                                                                                       |
| Start Node                    | If Start Automatically is turned on, the Dialogue Runner will start running this node when the scene starts. (If your Yarn Project does not contain a node with this name, an error will be reported.)                                                                                                                                                                                          |
| Run Selected Options as Lines | If this is turned on, when the user chooses an option, the Dialogue Runner will run the selected option as if it were a Line.                                                                                                                                                                                                                                                                   |
| Verbose Logging               | If this is turned on, the Dialogue Runner will log information about the state of each line to the Console as it's run.                                                                                                                                                                                                                                                                         |
| On Node Start                 | A Unity Event that's fired when the Dialogue Runner begins running a new node. This may be fired multiple times during a dialogue run.                                                                                                                                                                                                                                                          |
| On Node Complete              | A Unity Event that's fired when the Dialogue Runner reaches the end of a node. This may be fired multiple times during a dialogue run.                                                                                                                                                                                                                                                          |
| On Dialogue Complete          | A Unity Event that's fired when the Dialogue Runner stops running dialogue.                                                                                                                                                                                                                                                                                                                     |
| On Command                    | A Unity Event that's fired when a Command is encountered. This will only be called if no other part of the system has already handled the command, such as command handlers registered via [YarnCommand](../../api/csharp/yarn.unity/yarncommandattribute/) or [AddCommandHandler](../../api/csharp/yarn.unity/dialoguerunner/dialoguerunner.addcommandhandler-system.string-system.action.md). |

