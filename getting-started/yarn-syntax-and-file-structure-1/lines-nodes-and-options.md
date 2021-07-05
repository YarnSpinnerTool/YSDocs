# Lines, nodes and options

The core of Yarn is **lines of dialogue**. A line of dialogue is just the thing you want some entity or character to say, usually beginning with the name of the entity speaking.

```text
This is a line of dialogue.
Speaker: This is another line of dialogue said by someone called "Speaker".
```

Lines of dialogue can contain almost anything but if there is a set of characters without spaces before a colon \(:\) at the beginning of the line, this will be interpreted as the name of the character speaking. There are a few restricted characters that do specific things, but we'll get to that.

Every line of dialogue must be contained in a **node**. Nodes are used to separate out parts of the story and make it easier to manage longer stories and branching. Nodes are delineated by `---` and `===` markers which separate the node header and body. A node must have a title and, by convention, the node that should run first is titled **Start**.

```text
title: Start
---
Speaker: This is the first line of dialogue that will be run.
===
```

Here, content above the first horizontal line is the **node header**. Everything below the line is the body, and after the double line another node can start.

{% hint style="info" %}
Node headers can contain any number of lines with the structure **key: value** and this can be used to store additional information, such as the location the conversation is taking place. 
{% endhint %}

Back to dialogue, the first way to offer choices to the player is with **options**. Options are marked with a `->` symbol and present a number of possibilities of which only one will be selected. The content of the option is like any other line of dialogue. Any subsequent lines indented below an option will only run if that option is selected. 

```text
Companion: Hi there! What do you feel like doing today?
-> Player: I want to go swimming.
    Companion: Okay, let's go swimming.
-> Player: I'd prefer to go hiking.
    Companion: Cool, we'll go hiking then.
```

{% hint style="warning" %}
Node titles must not contain spaces. They must be made up of only letters, numbers and underscores, and the first character must be a letter. 

So **FirstNode**, **First**\_**Node** and **Node1** valid, but **First Node** and **1stNode** are not.
{% endhint %}

Options can be nested but the use of the `jump` command, enclosed within Yarn's `<< >>` command brackets, will allow dialogue to jump to and continue from a different node. This separation of dialogue segments into nodes makes for neater files that are easier to edit as they grow. 

{% tabs %}
{% tab title="Before" %}
```text
title: Start
---
Companion: Hi there! What do you feel like doing today?
-> I want to go swimming.
    Companion: Okay, let's go swimming.
    Companion: Where would you like to go swimming?
    -> The public pool.
    -> The beach.
-> I'd prefer to go hiking.
    Companion: Cool, we'll go hiking then.
    Companion: Have you got your hiking boots ready?
    -> Yes.
    -> No.
===
```
{% endtab %}

{% tab title="After" %}
```
title: Start
---
Companion: Hi there! What do you feel like doing today?
-> I want to go swimming.
    Companion: Okay, let's go swimming.
    <<jump Swimming>
-> I'd prefer to go hiking.
    Companion: Cool, we'll go hiking then.
    <<jump Hiking>>
===
title: Swimming
---
Companion: Where would you like to go swimming?
-> The public pool.
-> The beach.
===
title: Hiking
---
Companion: Have you got your hiking boots ready?
-> Yes.
-> No.
===
```
{% endtab %}
{% endtabs %}

Sometimes it makes sense for the options presented or the outcomes of selecting different options to vary based on other things the player has done or said up until this point. This requires the use of **logic** and **variables**.

