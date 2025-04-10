---
description: >-
  This example project demonstrates making a simple non-linear dialogue-based
  game when beginning with some pre-existing assets.
---

# 🛠️ NPC Dialogue Game

## Goals

1. Display Yarn dialogue in a Unity scene
2. Allow a player to select between options to respond
3. Allow a player to select among available characters to speak to
4. Use Yarn Spinner to trigger a command that changes the interactability of characters

## Materials

* Yarn Spinner installed in Unity
* Yarn Spinner set up in a text editor
* [**Starter Asset Package**](https://github.com/YarnSpinnerTool/ExampleProjects/releases/download/v2.0/Ghosty.Lads.Assets.unitypackage) downloaded and unzipped

## Instructions

Open a new Unity 3D project. Ensure Yarn Spinner has been added to the project in the Package Manager as per the [**Installation Instructions**](../installation-and-setup.md).

![](<../../../.gitbook/assets/Screen Shot 2022-01-27 at 2.56.06 pm.png>)

Drag the provided Asset Package into the **Project Window** where project files are displayed in Unity to import them into the project.

![The provided assets are being imported](<../../../.gitbook/assets/Screen Shot 2022-01-27 at 3.05.08 pm.png>)

This package includes the following assets and functionality:

1. A simple, static environment called **Graveyard** which also contains four character models.
2. A **C# script** that provides simple functions for the character objects.
3. A **Timeline** that stores the hovering animation for the Ghost character.
4. Some **Lights** that turn on and off to indicate when a Grave character is speaking.

![](../../../.gitbook/assets/assets.png)

### Creating a Runnable Script

{% hint style="success" %}
The next step is to import the Dialogue System and hook up a Yarn Project and Yarn Script. If you have completed [**Example Project 1**](example-project-1.md) or [**Example Project 2**](example-project-2.md) before, you may skip ahead to [**Filling Out Your Script**](example-project-3.md#filling-out-your-script). Otherwise, let's proceed!
{% endhint %}

Yarn Spinner for Unity comes with a pre-made UI layer and accompanying utility scripts to handle displaying lines and presenting options from Yarn files. Open the **GameObject menu**, and choose **Yarn Spinner > Dialogue System**.

![The Dialogue System has been added from the Project Window into the Scene](<../../../.gitbook/assets/Screen Shot 2022-01-27 at 3.57.19 pm.png>)

When the **Dialogue System** in the scene is selected, the **Inspector** will display the Yarn Project it is expecting line from. Here, a **Yarn Project** is a kind of linking file that groups Yarn script files together. To make one, navigate to a sensible place for the file to live (such as **Assets > Dialogue**) and right-click the **Project Window** pane to select **Create > Yarn Spinner > Yarn Project**.

{% hint style="info" %}
The existence of Yarn Projects allows larger games with multiple dialogue systems (e.g. main story dialogue, barks, storylets) to separate into multiple projects that pass lines to different UI or systems. This allows an extra level of organisation above separate Yarn files which are typically used to separate story scenes or parts.

However, most games will need only a single Yarn Project.
{% endhint %}

Select the scene's **Dialogue System** again and drag the new **Yarn Project** into the labelled slot in the **Inspector**.

![The new Yarn Project has been added to the Dialogue System's Dialogue Runner](<../../../.gitbook/assets/Screen Shot 2022-01-27 at 4.00.51 pm.png>)

Now the Yarn Project needs one or more **Yarn Scripts** to get dialogue from. Just like with the Yarn Project, navigate to the desired file location and select **Create > Yarn Spinner > Yarn Script**. Name it whatever you like - "GhostyLads" will do - and place it in the same folder as the Yarn Project.

![The new Yarn Script has been added to the Yarn Project's Source Scripts](<../../../.gitbook/assets/Screen Shot 2022-01-27 at 4.02.49 pm.png>)

### Filling Out Your Script

By default, a new Yarn Script begins with a single empty node with the name of the file. Open the file, rename the node to **Start** and put a single line of test dialogue.

```
title: Start
---
This is a line of test dialogue.
===
```

Returning to Unity, pressing the Play ▶️ button results in the test line being displayed in front of the graveyard scene. Pressing **Continue** will make the UI disappear, as it has reached the end of the script.

![The test line from the Yarn Script has been displayed in the otherwise non-interactable scene](<../../../.gitbook/assets/Screen Shot 2022-01-27 at 4.09.03 pm.png>)

It's time to plan a story. In the scene there are four characters—**Ghost**, **LeftGrave (Louise)**, **CenterGrave (Carol)**, and **RightGrave (Ruby)**—and the intent of this game is for the player to be able to interact with them in virtually any order to complete the objectives of the game. This game format typically accompanies stories where the player must piece together information from smaller tidbits given to them when they speak to different characters.

{% hint style="info" %}
For example: _neither Witness A nor B knew who stole the cookie from the kitchen, however:_

* _Witness A knew the cookie was taken in the morning._
* _Witness B knew that Suspects A and B entered the kitchen in the morning and afternoon, respectively._

_Together, their clues show that Suspect A must have eaten the cookie._
{% endhint %}

So, when the game begins, **Ghost** will present some mystery. Once a brief context-establishing conversation ends, the player will be free to select which character to speak to next. Speaking to each of the **Grave** characters will present a clue, provided the required prerequisite clues are known. At any time, the player can present their collated clues to Ghost. If their clues are complete, Ghost will tell them they solved the mystery and the game will end.

This short story provides a looping circuit through four paths, and results in the player reaching the ending after an undetermined number of conversations (though there is a hypothetical minimum, there is no maximum). A railroad diagram representation of the story would look as follows:

![](../../../.gitbook/assets/Artboard.png)

So it's time for the actual writing part. Here, I've opened my new Yarn Script in **Visual Studio Code** with the **Yarn Spinner Extension** installed as per the [**Installation Instructions**](broken-reference). I've written a minimal script that follows the planned story, as a skeleton that can be expanded on later.

![The new Yarn Script has been given some simple content](<../../../.gitbook/assets/Screen Shot 2022-01-28 at 12.27.13 pm (1).png>)

In this script, selecting the correct conversation option when speaking to each character will yield a new **clue**. However, the correct option is only available if the player has the required prerequisite clues. So no matter the order the player speaks to the graves, they must acquire clues in the order **A** then **B** then **C**.

{% hint style="info" %}
The most notable part about this script is that there are **no jump statements** in the file at all; each node is completely disconnected from the rest. Instead, we will be requesting and jumping to specific nodes manually from within Unity.
{% endhint %}

You can find this example script below to copy. Or if you want to make you own version and need a refresher on how to represent it in Yarn, refer to the [**Syntax and File Structure guide**](broken-reference).

<details>

<summary>GhostyLads.yarn</summary>

```
title: Start
---
<<set $hasClueA to false>>
<<set $hasClueB to false>>
<<set $hasClueC to false>>
Ghost: Welcome to the graveyard! Unfortunately, you're just in time for an unsolved mystery...
Ghost: You'll have to speak to these three to figure out what happened!
===
title: LeftGraveLouise
---
Louise: What do you want to know?
-> Something that will get me no clues?
-> Something that will get me Clue A? <<if not $hasClueA>>
    <<set $hasClueA to true>>
-> Something relating to existing Clue A? <<if $hasClueA>>
-> Something relating to existing Clue B? <<if $hasClueB>>
-> Something relating to existing Clue C? <<if $hasClueC>>
Louise: ~additional dialogue~
Louise: Ok, bye!
===
title: CenterGraveCarol
---
Carol: What do you want to know?
-> Something that will get me no clues?
-> Something that will get me Clue B? <<if $hasClueA and not $hasClueB>>
    <<set $hasClueB to true>>
-> Something relating to existing Clue A? <<if $hasClueA>>
-> Something relating to existing Clue B? <<if $hasClueB>>
-> Something relating to existing Clue C? <<if $hasClueC>>
Carol: ~additional dialogue~
Carol: Ok, bye!
===
title: RightGraveRuby
---
Ruby: What do you want to know?
-> Something that will get me no clues?
-> Something that will get me Clue C? <<if $hasClueB and not $hasClueC>>
    <<set $hasClueC to true>>
-> Something relating to existing Clue A? <<if $hasClueA>>
-> Something relating to existing Clue B? <<if $hasClueB>>
-> Something relating to existing Clue C? <<if $hasClueC>>
Ruby: ~additional dialogue~
Ruby: Ok, bye!
===
title: Ghost
---
Ghost: Are you ready to tell me what happened?
-> Yes
    Ghost: Well, what do you know?
    -> I have no clues.
    -> I have clue A. <<if $hasClueA>>
    -> I have clues A and B. <<if $hasClueB>>
    -> I have clues A, B and C. <<if $hasClueC>>
        <<jump Ending>>
    Ghost: That doesn't sound right...
-> No
Ghost: Go on and speak to those three!
===
title: Ending
---
Ghost: You solved it!
===
```

</details>

Once you've got a basic story, pop back into Unity and check the basics:

* [x] Lines display correctly
* [x] Pressing **Continue** advances lines correctly
* [x] Selecting different options have the expected outcomes

![Yarn Spinner is displaying lines, advancing lines and selecting options correctly as per the script](<../../../.gitbook/assets/Screen Shot 2022-01-27 at 4.58.59 pm.png>)

{% hint style="warning" %}
Note that at this point, there is no way to progress beyond the intro conversation with Ghost. All other nodes cannot be reached with the code we have written so far.
{% endhint %}

### Making Players Interactable

In this game, the player should be able to select an NPC in the scene and have it trigger their repsective conversation. This requires a few things:

* Code to **begin dialogue from a specific node** when a character object is interacted with.
* Code to **disable scene interaction** when any character is already speaking.
* Code to **disable character interaction** when a specific character should not be interactable.

In **Assets > Scripts** there is a C# script that has code to do these things (see headers below), so we just need to connect it to the appropriate places. But first, let's step through what it does.

{% tabs %}
{% tab title="YarnInteractable.cs" %}
```cpp
// this file is attached to every character in the scene and so will affect only
// the targeted character object when functions are called

// disable scene interaction, activate speaker indicator, and
// run dialogue from {conversationStartNode}
private void StartConversation();

// reverse StartConversation's changes: 
// re-enable scene interaction, deactivate indicator, etc.
private void EndConversation();

// make character not able to be clicked on
public void DisableConversation();
```
{% endtab %}
{% endtabs %}

Add the **YarnInteractable** script to each character in the game: Ghost, LeftGrave, CenterGrave, and RightGrave. Make sure to set their respective `conversationStartNode` values in the Inspector to match what they are called in the Yarn script.

![A character is made interactable through the addition of the YarnInteractable script with the correct conversationStartNode value](<../../../.gitbook/assets/Screen Shot 2022-01-28 at 1.45.35 pm.png>)

First up is the code for beginning a conversation. This requires **running dialogue** from a **specific node** when a character is **interacted with**. Running dialogue is a simple matter of telling the **DialogueRunner** to begin dialogue and passing the name of the node to begin from as a string.

```cpp
// first we need a handle on the DialogueRunner, so we may as well get it when
// this object is first added to the scene
private DialogueRunner dialogueRunner;

public void Start() {
    dialogueRunner = FindObjectOfType<Yarn.Unity.DialogueRunner>();
}

// then we need a function to tell Yarn Spinner to start from {specifiedNodeName}
public string conversationStartNode;

private void StartConversation() {
    dialogueRunner.StartDialogue(conversationStartNode);
}
```

To run this when a character is interacted with, simple override the `OnMouseDown()` function that exists for every **GameObject** (which this class inherits from). Checking the `IsDialogueRunning` property of the **DialogueRunner** is a simple way to ignore interaction whenever starting dialogue would interrupt an existing conversation.

```cpp
private bool interactable; // whether this character should be enabled right now
// (begins true, but may not always be true)

public void OnMouseDown() {
    // if this character is enabled and no conversation is already running
    if (interactable && !dialogueRunner.IsDialogueRunning) {
        // then run this character's conversation
        StartConversation();
    }
}
```

This handles beginning a conversation, but what if other changes are needed while a character is speaking? Well, having a function that is triggered when a conversation _ends_ would allow properties to be set in `StartConversation` that can then be reversed once dialogue has ended.

{% hint style="danger" %}
In a typical game, several changes would be triggered when beginning or ending dialogue, such as changing UI mode and starting and stopping a speaking animation on the relevant character or similar. So it's sensible to have bookend functions that hold all this code, even if we won't be doing anything useful with `EndConversation()`until later.
{% endhint %}

To trigger a function when a conversation ends, a **listener** can be added to the **DialogueRunner** that will fire a specified function when a certain event occurs. The `onDialogueComplete` event happens whenever the runner reaches the end of its current conversation path.

```cpp
// this would go in the Start() function, right after finding the DialogueRunner
// object, so that the listener begins before dialogue does the first time
dialogueRunner.onDialogueComplete.AddListener(EndConversation);
```

Next, let's define the function it will call. A key consideration here is that **every object** using this YarnInteractable script will be notified of dialogue completion every time it happens. Each one is registering a listener, and each will have its own `EndConversation()` function be called.

So to save some work, we can check whether this is the instance that should care about the event. This can be done just by setting a boolean when the conversation begins, that says this is the character that is currently speaking.

```cpp
private bool isCurrentConversation;

private void StartConversation() {
    isCurrentConversation = true;
    // TODO *begin animation or turn on speaker indicator or whatever* HERE
    dialogueRunner.StartDialogue(conversationStartNode);
}

private void EndConversation() {
    if (isCurrentConversation) { 
        // TODO *stop animation or turn off indicator or whatever* HERE
        isCurrentConversation = false;
    }
}
```

Returning to Unity, press the ▶️ button and see that this now allows a new conversation to be triggered by **interacting with any character** after another has finished speaking.

![Clicking on a YarnInteractable object runs the corresponding node dialogue](<../../../.gitbook/assets/Screen Shot 2022-01-28 at 1.43.02 pm.png>)

At this point, this may seem done, but there is a critical issue here. Looking back at the earlier goals:

* [x] Clicking on a character **begins dialogue** from their respective node.
* [x] Clicking on a character **while dialogue is already running** does nothing.
* [ ] Clicking on a character **when they should not be interactable** does nothing.

Why that third thing? Well, because the current state of the game allows the player to:

1. Speak to the Ghost to begin the story.
2. Ask the Graves about the mystery.
3. Speak to the Ghost once they have collected the necessary clues.
4. Have Ghost tell them they ✨ solved the mystery ✨ and say goodbye.
5. Go back and still ask the Graves about the mystery that is already solved(?!)

So there needs to be a way to tell a specific character "no, you are done, don't speak to the player any more". This can be done with a simple **Yarn Command**.

In **YarnInteractable.cs** there is a simple function that sets a flag that the `OnMouseDown()` function checks when deciding whether to start a conversation. Turning this into a command simple requires adding the **Yarn Command** decorator above the function, with the string that will become the command keyword in any yarn scripts.

```cpp
[YarnCommand("disable")]
public void DisableConversation() {
    interactable = false;
}
```

{% hint style="info" %}
If you're using Unity 2021.1 or earlier, once you've made this change to your code, open the Window menu and choose Yarn Spinner -> Update Yarn Commands to update the code that makes this command available to your Yarn scripts.
{% endhint %}

Back in the Yarn script, call `disable` once for each character when the story ends, to save the player from going back and having a confusion conversation about an already-solved mystery.

```
title: Ending
---
Ghost: You solved it!
<<disable Ghost>>
<<disable LeftGrave>>
<<disable CenterGrave>>
<<disable RightGrave>>
===
```

And that's it for the dialogue behaviours! Back in Unity, characters should speak when interacted with—but not when it would interrupt another, or when the story has ended.

![Characters can now be selected and will speak when appropriate](<../../../.gitbook/assets/Screen Shot 2022-01-28 at 1.18.39 pm.png>)

### Draw the Rest of the Owl

Now that all the behaviours are working and the skeleton story plays through correctly, it's time to replace the skeleton placeholder script with the full story and add some polish. Delete the Yarn Script that you created earlier, and find the **GhostyLads\_FinalVersion.yarn** file in the **Assets > Dialogue** folder. Move it into the same folder as the Yarn Project.

![The Yarn script for the Scene has been replaced with a full story version](<../../../.gitbook/assets/Screen Shot 2022-01-28 at 1.23.24 pm (1).png>)

Next, let's add an **indicator** so the player more easily knows which character is **currently speaking**.

{% hint style="warning" %}
_Because I am not an animator, I have used only static objects as characters in this demo game. To indicate who is speaking, I will be using a simple spotlight that turns on and off above the speaker. I will not be taking questions at this time._—Mars, 2022.
{% endhint %}

In the scene, each grave object also contains a **green spotlight** which is currently assigned to a variable called `lightIndicatorObject` in **YarnInteractable.cs**, so a snippet of code in each of the`StartConversation()` and `EndConversation()` functions can quickly turn it on and off for the relevant character.

```cpp
private void StartConversation() {
    isCurrentConversation = true;
    if (lightIndicatorObject != null) {
        lightIndicatorObject.intensity = defaultIndicatorIntensity;
    }
    dialogueRunner.StartDialogue(conversationStartNode);
}

private void EndConversation() {
    if (isCurrentConversation) {
        if (lightIndicatorObject != null) {
            lightIndicatorObject.intensity = 0;
        }
        isCurrentConversation = false;
    }
}
```

Now, a light should turn on above any grave who is currently speaking.

![The current speaker is now indicated by a green spotlight](<../../../.gitbook/assets/Screen Shot 2022-01-28 at 1.53.55 pm.png>)

## Result

A playable whodunnit-like game with multiple characters that can be spoken to in any order to solve a mystery from partial clues available.

![The game is complete and playable with characters that can be spoken to in any order](<../../../.gitbook/assets/Screen Shot 2022-01-28 at 1.38.03 pm.png>)

An easy way to spice this up is to just try replacing provided assets with ones of your own choosing. There are plenty of publically available asset packs with permissive licenses to play with, and re-theming a starter game and building from there can be easier than starting from scratch.

You could add more characters, or even design a more complex conversation structure that must be navigated to solve the mystery! Yarn Spinner is great at telling complex non-linear stories where player choices matter.
