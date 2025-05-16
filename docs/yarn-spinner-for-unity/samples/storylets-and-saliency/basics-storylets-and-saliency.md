---
description: >-
  Learn about the Basics Storylets and Saliency Sample, which shows off the
  fundamentals of Yarn Spinner's saliency systems.
---

# Basics Storylets and Saliency

Yarn Spinner 3 introduced **storylets**, a powerful new way to select which content should be presented to players.&#x20;

{% hint style="info" %}
For more on this topic we have [storylets-and-saliency-a-primer.md](../../../write-yarn-scripts/advanced-scripting/storylets-and-saliency-a-primer.md "mention"), which explores the concept in the abstract, and a sample and guide on [custom-saliency-strategies.md](custom-saliency-strategies.md "mention") and [advanced-saliency.md](advanced-saliency.md "mention").
{% endhint %}

Storylets allow you to break your narrative into modular chunks, with a **saliency strategy** determining which chunk should run next based on game state and other factors.

Yarn Spinner provides two different approaches to storylets, [node-groups.md](../../../write-yarn-scripts/advanced-scripting/node-groups.md "mention") and [line-groups.md](../../../write-yarn-scripts/scripting-fundamentals/line-groups.md "mention"), along with several [saliency.md](../../../write-yarn-scripts/advanced-scripting/saliency.md "mention") strategies to fit your specific needs.&#x20;

This guide focuses on getting you comfortable with the basics of storylets in Yarn Spinner.

### What we'll be covering

* Writing node group storylets
* Writing line group storylets
* Calling salient content
* Interacting with generated variable storage systems

### The Sample

![The Basic Saliency Sample](<../../../.gitbook/assets/01 (2).png>)

Our **Basic Storylets and Saliency Sample** demonstrates various things you can do with **storylets** in Yarn Spinner:

* Content for three in-game days (Monday, Tuesday, and Wednesday)
* Two time periods each day (morning and evening)
* A time advancement mechanic in the center of the scene
* Several characters showcasing different approaches to storylets

{% include "../../../.gitbook/includes/you-can-learn-how-to-add-th....md" %}

#### The Time Advancer

The time advancer controls what day and time the NPCs respond to. Each time you press the button, time advances one step through the sequence:

* Monday morning → Monday evening → Tuesday morning → and so on.
* When reaching Wednesday evening, it wraps back to Monday morning

The implementation is straightforward: when you collide with the trigger, it calls the `AdvanceTime()` method and updates the plinth label via `UpdateLabel()`.&#x20;

Both methods work by reading and modifying Yarn variables (`$day` and `$time`) through a generated variable storage class.

Yarn Spinner allows you to **generate a variable storage class** that provides convenient wrappers around your declared variables. The system automatically regenerates this file whenever you change your Yarn files or project settings.

{% hint style="info" %}
You can learn more about [variable-storage](../../../components/variable-storage/ "mention"), if you're curious.
{% endhint %}

![Generated variable storage section of the project inspector](<../../../.gitbook/assets/02 (1).png>)

This creates two properties on the class—`Day` and `Time`—which you can access directly in your code. The Yarn Spinner-generated code:

* Handles all standard variable storage lookup operations
* Performs type checking automatically
* Significantly reduces the amount of code you need to write
* Generates enums matching the types defined in the `Setup` node

#### The NPCs

Each NPC in the scene demonstrates a different aspect of storylets through their `DialogueInteractible` component.&#x20;

This component determines which node runs when the player interacts with the character.

![The Dialogue Interactible inspector for Alice](<../../../.gitbook/assets/03 (1).png>)

The component pulls available nodes directly from the attached Yarn project. When triggered, it simply tells the DialogueRunner to run the selected node—just like if you wrote `<<jump npc_name>>` in your Yarn Spinner Script.

Each NPC runs a single entry node, and the storylets system handles the rest. But how do storylets actually work in practice?

## Writing Storylets in Yarn Spinner

While storylet implementation depends heavily on your specific narrative needs, our sample focuses on a common use case: NPCs making contextual comments based on the current day and time.

This example functions as a "barks" demo—short, reactive dialogue lines—which provides an excellent introduction to storylets and salient content. Each NPC demonstrates a different approach to storylets, all defined in the `BasicSaliency.yarn` file.

### George and Line Groups

George demonstrates the simplest approach using [line-groups.md](../../../write-yarn-scripts/scripting-fundamentals/line-groups.md "mention").

Each line in a block that starts with `=>` represents one potential candidate for selection in that line group. Yarn Spinner chooses only a single line to present each time the line group is reached.

George's dialogue includes:

* Two generic lines with no conditions (can run anytime)
* Three conditional lines that filter based on the current day
* One line with nested content that runs if that line is selected

For example, the line `=> another Monday, I hate Mondays <<if $day == .Monday>>` will only be shown if the current day is Monday.

### Liz, Node Groups, and When Always

Liz demonstrates [node-groups.md](../../../write-yarn-scripts/advanced-scripting/node-groups.md "mention") with the "always" condition.

A node group consists of multiple nodes sharing the same `title`. When selecting which node to run, Yarn Spinner examines the `when` headers to determine what should be shown.

Liz's nodes all use the `when: always` header, indicating they're always valid choices. This special header is particularly useful for fallback content.

One of Liz's nodes uses another special header, `when: once`, which tells Yarn Spinner this node should only be shown once. After being selected, it will never appear again—perfect for character introductions or one-time events.

### Barry and Conditionals

Barry also uses node groups, but with conditional expressions in the `when` headers.

Each of Barry's nodes checks the time of day using expressions like `when: $time == .Morning` or `when: $time == .Evening`. This means that every time you talk to Barry, half of his potential dialogue nodes are filtered out based on the current time.

This approach lets you easily filter nodes to present only content appropriate to the current game state.

### Alice and Multiple Whens

Alice demonstrates the most specific approach with multiple `when` conditions.

Each of her nodes contains multiple `when` clauses, creating highly specific combinations of day and time conditions. This gives Alice the most contextually appropriate responses but requires the most content creation.

This highlights an important tradeoff: greater specificity requires more storylets. However, this is also a strength of the system. You can:

* Use fallback storylets (like Liz's) for situations that don't need specific responses
* Omit storylets for combinations where characters have nothing important to say
* Create a more precisely woven narrative landscape with less effort than traditional approaches

### Nodes Groups and Titles

Most NPCs in our sample use node groups, meaning their nodes share the same title. While this would normally cause an error in Yarn Spinner, it's intentional with storylets.

Any nodes with the same name become part of the same node group. When that group is requested to run, Yarn Spinner selects one node to present.

**Important requirements for node groups:**

1. Each node in the group must share the same title
2. Every node must have at least one `when` header to be recognized as part of a group
3. If you don't have specific conditions, use `when: always` as a fallback

Learn more about [node-groups.md](../../../write-yarn-scripts/advanced-scripting/node-groups.md "mention").

### The Saliency Strategy

With multiple potential storylets available, how does Yarn Spinner decide which one to show?

This is handled by the **saliency strategy**, which selects the most appropriate content while resolving ambiguity.

The default strategy (used in this sample) is "Random Best Least Recently Seen," which:

1. Removes any storylets with failing conditions
2. Counts the conditions on each viable storylet to determine its "complexity"
3. Selects the storylet with the highest complexity (most conditions)
4. If multiple storylets tie for complexity, deprioritizes any that have been recently seen
5. If there's still a tie, makes a random selection

This approach typically provides the best experience in most narrative situations, balancing specificity with variety. Yarn Spinner includes other built-in strategies, and you can create custom strategies for precise control over content selection.

## Conclusion

**Storylets** provide a **flexible and powerful way to organize narrative content** in Yarn Spinner. By breaking your story into modular chunks and using saliency strategies to select the most appropriate content, you can create dynamic, responsive narratives that adapt to your game state.

Whether you're implementing character barks, branching dialogues, or more complex narrative systems, storylets offer a streamlined approach to creating engaging, reactive stories in your games.
