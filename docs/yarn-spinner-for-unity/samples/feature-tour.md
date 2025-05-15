---
description: >-
  Learn about the Feature Tour Sample, which shows off many of the different
  capabilities of Yarn Spinner.
---

# Feature Tour

![The Feature Tour Sample.](../../.gitbook/assets/gauntlet-01.png)

The Feature Tour Sample is an ideal starting point for newcomers to Yarn Spinner. It presents a series of conversations along a corridor, each demonstrating a different capability of Yarn Spinner.

Are you ready to navigate this narrative gauntlet?

## Features Covered

* [Nodes, Lines](../../write-yarn-scripts/scripting-fundamentals/lines-nodes-and-options.md) and [Options](../../write-yarn-scripts/scripting-fundamentals/options.md)
* [Jumps](../../write-yarn-scripts/scripting-fundamentals/jumps/) and [Detours](../../write-yarn-scripts/scripting-fundamentals/jumps/detour.md)
* [Variables and Interpolation](../../write-yarn-scripts/scripting-fundamentals/logic-and-variables/)
* [Flow Control and Branching](../../write-yarn-scripts/scripting-fundamentals/logic-and-variables/flow-control.md)
* [Commands](../../write-yarn-scripts/scripting-fundamentals/commands.md) and [Functions](../../write-yarn-scripts/scripting-fundamentals/functions.md)
* Storylets
* A Dialogue Interactible component and node-character associations

## Tour Structure

The feature tour consists of a long corridor with multiple rooms. Each room contains one or more interactive characters, with each character showcasing a specific Yarn Spinner feature. While this sample doesn't demonstrate every Yarn Spinner capability, it covers the most commonly used ones.

### Dialogue Interactible Component

At the heart of this feature tour is a class, **Dialogue Interactible**. This component is attached to each interactive character and associates a specific dialogue node with that character. If you're curious about how a particular feature works, you can identify which node contains that feature through this component.

![Sally talking about variables](../../.gitbook/assets/gauntlet-02.png)

For example, if you want to see which node provides dialogue for a specific character, select that character in the scene and examine the Dialogue Interactible component.

![Sally's dialogue interactible component](../../.gitbook/assets/gauntlet-03.png)

In this example, we can see the node is `Room4_Variables_2`. Since all dialogue in this sample is contained in a single file (`Tour.yarn`), you simply need to open that file and locate the node to understand its implementation.
