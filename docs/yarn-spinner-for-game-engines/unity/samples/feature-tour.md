# 🚧 Feature Tour

![The feature tour](../../../.gitbook/assets/gauntlet-01.png)

The feature tour is the best starting point if you are new to what Yarn Spinner can do.
It's a gaggle of conversations, down a long corridor, each showing off a different element of Yarn Spinner.
Dare you traverse the narrative gauntlet?

## What we'll be covering

- Lines and Options
- Jumps and Detours
- Variables and Interpolation
- Ifs and Branching
- Commands and Functions
- Storylets
- The dialogue interactible and associating nodes with characters

## The Gauntlet Structure

The feature tour is a long corrider with multiple rooms spread out across it.
Each room has one or more characters within it you can talk to and every character shows off a different feature of Yarn Spinner.
While this sample doesn't show off every feature of Yarn Spinner it shows off the most common ones.

### Dialogue Interactible

The core of this feature tour is in the Dialogue Interactible class.
This is a component on each of the characters you can speak to and allows you to associate a particular node with that character.
If at any time you are curious *how* a particular feature works you can see which node that contains that feature from this component.

![Sally talking about variables](../../../.gitbook/assets/gauntlet-02.png)

So for example if you wanted to see which node this character is pulling it's dialogue from you could select the character in the scene and then check the Dialogue Interactible component.

![Sally's dialogue interactible component](../../../.gitbook/assets/gauntlet-03.png)

In this case we can see that it happens to be `Room4_Variables_2`, and as all the dialogue in this sample is in the one file `Tour.yarn` you just need to open that file and find that node to see how it works.
