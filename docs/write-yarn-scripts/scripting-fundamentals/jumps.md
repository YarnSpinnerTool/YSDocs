---
description: Learn to use the jump command to move the narrative between nodes.
icon: diagram-sankey
---

# Jump Command

The `<<jump>>` command lets you move the dialogue between nodes. It is used by writing `<<` then the word `jump`, a space, and then the full title of the node you want to jump the narrative to, then another `>>`.&#x20;

To jump to a node with the title `Rescue_the_Kitten` , for example, you would write the line <kbd><\<jump Rescue\_the\_Kitten>></kbd>.&#x20;

Jump commands should always be placed on their own line, indented as appropriate.

## Using the Jump Command

For example, consider the following conversation, which could be structured inside one node, using nested options, or split over several nodes using options and jump commands. The before version is inside a single node, and works fine, but the after version is structured across multiple nodes, and is a lot easier to make sense of.&#x20;

{% tabs %}
{% tab title="Before" %}
```
title: Start
---
Navigator: Where to, Captain?

-> Captain: I want to go back to earth!
    Navigator: Earth it is sir. 
    Navigator: This jump will take us 10 hours.
    Navigator: Permission to jump, sir?
    -> Captain: Granted, let's go!
        Navigator: On it, sir.
    -> Captain: Not yet. Just wait a moment.
        Navigator: Standing by, sir.
-> Captain: Second star to the left!
    Navigator: Can you be more specific?
    -> Captain: I cannot, no.
        Navigator: Right away, sir.
    -> Captain: ... that one *gestures*
        Navigator: Very good, sir.

Navigator: Being a Navigator sure is hard work!
===
```
{% endtab %}

{% tab title="After" %}
```
title: Start
---
Navigator: Where to, Captain?

-> Captain: I want to go back to earth!
    <<jump Earth>>
-> Captain: Second star to the left!
    <<jump SecondStar>>
    

Navigator: Being a Navigator sure is hard work!
===

title: Earth
---
Navigator: Earth it is sir. 
    Navigator: This jump will take us 10 hours.
    Navigator: Permission to jump, sir?
    -> Captain: Granted, let's go!
        Navigator: On it, sir.
    -> Captain: Not yet. Just wait a moment.
        Navigator: Standing by, sir.
<<jump Done>>
===

title: SecondStar
---
Navigator: Can you be more specific?
    -> Captain: I cannot, no.
        Navigator: Right away, sir.
    -> Captain: ... that one *gestures*
        Navigator: Very good, sir.
<<jump Done>>
===

title: Done
---
Navigator: Being a Navigator sure is hard work!
===
```
{% endtab %}
{% endtabs %}

Separating dialogue segments into nodes can aid in writing neater files that are easier to edit as they grow.

When you use `<<jump>>` command, they'll be shown in the Graph View in Yarn Spinner for Visual Studio Code as an line with an arrow leading to the node that's being jumped to:

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-15 at 12.21.38 pm.png" alt=""><figcaption><p>The <code>&#x3C;&#x3C;jump>></code> command being visualised in the Graph View.</p></figcaption></figure>

If you use the `<<jump>>` command to jump to a node that's in a different `.yarn` file, it will be visualised as a line leading to a small circle:

<figure><img src="../../.gitbook/assets/Screenshot 2025-07-10 at 8.25.36 pm.png" alt=""><figcaption></figcaption></figure>

## Write some Jump Commands

{% stepper %}
{% step %}
### Write a simple story with several nodes.

Spread your story out over the nodes in a sensible manner.
{% endstep %}

{% step %}
### Use the `<<jump>>` command to move between nodes in your story.

Make sure you specify the name of the node you want to jump to inside each `<<jump>>` command.
{% endstep %}

{% step %}
### Run your story using Preview.

Play through it, and make sure the jumps behave as you'd expect.
{% endstep %}
{% endstepper %}

Next up, learn about the Jump Command's close relative, the [detour.md](detour.md "mention").
