---
icon: diagram-sankey
---

# Jumps

You can nest options as much as you like. However, this can get a bit challenging to read. It's often a good idea to use the `<<jump>>` command to jump to a different node:

{% tabs %}
{% tab title="Before" %}
```
title: Start
---
Companion: Hi there! What do you feel like doing today?

-> Player: I want to go swimming.
    Companion: Okay, let's go swimming.
    Companion: Where do you want to swim?
    -> Player: The lake!
        Companion: Nice! It's a great day for it.
    -> Player: The swimming pool!
        Companion: Oh, awesome! I heard they installed a new slide.
-> Player: I'd prefer to go hiking.
    Companion: Cool, we'll go hiking then.
    
Player: Sounds good!
===
```
{% endtab %}

{% tab title="After" %}
```
title: Start
---
Companion: Hi there! What do you feel like doing today?

-> Player: I want to go swimming.
    Companion: Okay, let's go swimming.
    <<jump Swimming>>
-> Player: I'd prefer to go hiking.
    Companion: Cool, we'll go hiking then.
    <<jump Hiking>>
===
title: Swimming
---
Companion: Where do you want to swim?
-> Player: The lake!
    Companion: Nice! It's a great day for it.
-> Player: The swimming pool!
    Companion: Oh, awesome! I heard they installed a new slide.

<<jump Done>>
===
title: Hiking
---
Companion: Have you got your hiking boots ready?
-> Player: Yes.
    Companion: Great, let's go!
-> Player: No.
    Companion: We can swing by your place and pick them up!

<<jump Done>>
===
title: Done
---
Player: Sounds good!
===
```
{% endtab %}
{% endtabs %}

Separating dialogue segments into nodes can aid in writing neater files that are easier to edit as they grow.

Sometimes it makes sense for the options presented or the outcomes of selecting different options to vary based on other things the player has done or said up until this point. This requires the use of **logic** and **variables**, which we'll discuss in the next section.
