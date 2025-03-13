---
description: Learn to use the jump command to move the narrative between nodes.
icon: diagram-sankey
---

# Jumps

The `<<jump>>` command is used by writing `<<` then the word `jump`, a space, and then the full title of the node you want to jump the narrative to, then another `>>`.

For example, to jump to a node with the title `Rescue_the_Kitten` you would write <kbd><\<jump Rescue\_the\_Kitten>></kbd>. You should place jump&#x20;

Yarn Spinner Scripts can get pretty complex pretty fast, so it's a good idea to use the `<<jump>>` command to jump to a different node to keep sections of dialogue cleanly separated.&#x20;

**For example, consider the following conversation, whic could be structured inside one node, using nested options, or split over several nodes using options and jump commands:**

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

{% stepper %}
{% step %}
### Using Try Yarn Spinner, write a story with several nodes.

Spread your story out over the nodes in a sensible manner.
{% endstep %}

{% step %}
### Use the <\<jump>> command to move between nodes in your story.

Make sure you specify the name of the node you want to jump to inside each <\<jump>> command.
{% endstep %}

{% step %}
### Run your story using Try Yarn Spinner.

Play through it, and make sure the jumps behave as you'd expect.
{% endstep %}
{% endstepper %}
