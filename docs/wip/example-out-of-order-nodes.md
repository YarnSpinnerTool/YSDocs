---
description: >-
  This example snippet demonstrates how to do away with the Yarn conversation
  tree approach and instead allow players to interact with NPCs or trigger
  conversations in any order.
---

# 📝 Example: Out-Of-Order Nodes

{% hint style="warning" %}
This document is **not yet complete.**
{% endhint %}

Yarn scripts are typically used to construct trees of conversation dialogue. Player selection among predefined options at given points will define the path through the tree they take, but the tree still has a beginning and a continous stream of dialogue lines and options until an end is reached. This is the default use of Yarn Spinner if you drag in a Yarn script and press play.

However, the `DialogueRunner` object that delivers lines from Yarn scripts to Unity has a few simple functions and properties that can be leveraged to implement custom behaviours. Maybe the simplest is allowing players to trigger segments of dialogue in different orders.

So say you wanted to make a game like a Murder Mystery where the player is sent into a room and told to question everyone until they have enough information to catch the culprit. Writing a conversation tree for such a thing would require nodes with as many options as there are characters—to start the right conversation—and conversations would immediately return there to select the next conversation. It would be horribly inefficient and not very fun to write, not to mention require the player to always be in a conversation with either an NPC or the hub.

Instead, let's take advantage of the `DialogueRunner`'s `StartDialogue()` function.

If the prefab Dialogue System included with Yarn Spinner for Unity is used, pressing ▶️ in Unity will run the `StartDialogue()` function with whatever the **starting node name** is \(defaulting to **Start**\). And when the end of the script is reached, the Runner will stop. If at any time \(whether the Runner is already running a conversation or not\), the `StartDialogue()` function is called it will run the script over again from the starting node but will not reset the state of any variables used by the script.

The function can also take an optional **parameter** of a different node name to start running from. We can use this to allow the player to select an object in the scene and have the Runner kick off the correct dialogue, and this in turn will allow dialogue to end completely in between conversations.

All this needs on the Unity side is a single, short C\# script:

```csharp
using UnityEngine;
using Yarn.Unity;

public class YarnInteractable : MonoBehaviour
{
    [SerializeField] public string conversationStartNode;
    private DialogueRunner dialogueRunner;

    public void Start() {
        dialogueRunner = FindObjectOfType<Yarn.Unity.DialogueRunner>();
    }

    public void OnMouseDown() {
        if (!dialogueRunner.IsDialogueRunning) {
            Debug.Log($"Starting conversation with {name}.")
            dialogueRunner.StartDialogue(conversationStartNode);
        }
    }
}
```

This script, if placed on an _interactable_ \(i.e. clickable, etc.\) GameObject in the Scene will do two simple things:

1. **When the object is first created** and the `Start()` function is called, it will find the Dialogue Runner in the Scene and save a reference to it in a variable called `dialogueRunner` so it doesn't have to find it again whenever it needs to tell it something.
2. **When the object is clicked** and the `OnMouseDown()` function is called, it will check whether the player is already in a conversation \(with this object or any other\) and if not, it will tell `dialogueRunner` to start running dialogue for this object.

When placed on an object in 

