---
description: If you're totally new to Yarn Spinner, this is the place to start.
icon: star-christmas
---

# Beginner's Guide

## Writing Yarn with Try Yarn Spinner

When you first start learning Yarn, you can use [**Try Yarn Spinner**](https://try.yarnspinner.dev/), our introductory, browser- based tool for writing Yarn Spinner Scripts. No installation necessary!

{% hint style="info" %}
As you learn to write dialogue and game scripts with Yarn, you'll eventually need to use our editor, which is a Visual Studio Code Extension. Before you get to that stage, the best place to experiment with, and explore Yarn Spinner, is [Try Yarn Spinner](https://try.yarnspinner.dev). We strongly recommend that you learn piece by piece.
{% endhint %}

{% stepper %}
{% step %}
## Visit **Try Yarn Spinner** at [https://try.yarnspinner.dev](https://try.yarnspinner.dev/)

In **Yarn**, everything you write is text and structured around **nodes** and **lines**.

In **Try Yarn Spinner**, the first node to run is always called **Start**, so we’ll write that now.

{% hint style="info" %}
In your own games or narratives outside of Try Yarn Spinner, the first node can be named whatever you like.
{% endhint %}
{% endstep %}

{% step %}
## **Create a Start node with a line of dialogue**

Copy and paste, or write, this Yarn Spinner script into Try Yarn Spinner, and hit the Run button in the top-right.&#x20;

<pre class="language-markup" data-line-numbers><code class="lang-markup"><strong><a data-footnote-ref href="#user-content-fn-1">title: Start</a>
</strong><a data-footnote-ref href="#user-content-fn-2">---</a>
<a data-footnote-ref href="#user-content-fn-3">Narrator:</a> Hi, I'm the narrator for the documentation!
<a data-footnote-ref href="#user-content-fn-4">===</a>
</code></pre>

This is a **node**. A node must always start with a **header** containing a single **key** and **value** pair to set the node's **title**. The key is **`title`** and the value is `Start` . They are separated by a `:` .  Node titles must start with a letter, and can only contain letters, numbers and underscores.&#x20;

The header ends with a line containing only `---` and the **body** of the node follows. The body is where the **lines** are kept.&#x20;

There is a single **line** here: `Narrator: Hi, I'm the narrator for the documentation!` A line can contain whatever you want, and doesn't have to begin with a character name.&#x20;

Finally, the node ends with a line containing only `===`.
{% endstep %}

{% step %}
## **Play your Yarn Script**

Use the Run button in the top right-hand corner of Try Yarn Spinner to run your Yarn Spinner Script. You can play through it in the right pane. There isn't much to play right now!

<figure><img src=".gitbook/assets/Screenshot 2025-03-07 at 1.22.45 pm.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## Add a two more nodes

In the left-hand pane of Try Yarn Spinner, add a new node by copy and pasting, or writing, the following snippet of Yarn Spinner script. Place it below the previous node.

```markup
title: Adventure
---
Narrator: We're going to go on an adventure!
===

title: Cave
---
Narrator: Let's look inside the spooky cave...
===
```

You may want to Run the Yarn Spinner Script to see what happens. You'll probably notice that nothing has changed!

That's because there is currently no path to these nodes from the Start node. To add a path, you'll need to use the **jump command**.&#x20;
{% endstep %}

{% step %}
## Add a Jump Command

Update the contents of the `Start` node, and add a jump command, like this:

<pre class="language-markup"><code class="lang-markup"><strong>title: Start
</strong>---
Narrator: Hi, I'm the narrator for the documentation!
<a data-footnote-ref href="#user-content-fn-5">&#x3C;&#x3C;jump Adventure>></a>
===
</code></pre>

All commands in Yarn Spinner are surrounded by `<<` and `>>`. A jump command contains the `jump` keyword, and then the title of the node you want to jump to.&#x20;

So, this particular jump command will jump to the node titled `Adventure`.
{% endstep %}

{% step %}
## Play your Yarn Spinner Script again

Use the Run button in the top right-hand corner of Try Yarn Spinner to run your Yarn Spinner Script again. Your story is now slightly more interesting!

You'll notice that when the line containing the jump command arrives, the story continues in the node that was jumped to so you'll now also see the line `Narrator: We're going to go on an adventure!`&#x20;

Our story isn't particularly amazing, but we still have another node that's not being used...
{% endstep %}

{% step %}
## Introducing Options

We're going to introduce one final concept in this Beginner's Guide: Options.

Update your Adventure node to look like the following:&#x20;

The lines the start with `->` are known as **options**. Options provide a choice to the player and always begin with a `->`. &#x20;

```
title: Adventure
---
Narrator: We're going to go on an adventure!
-> OK! Let's go!
    <<jump Cave>>
-> I don't want to go on an adventure...
    Narrator: Oh, OK then.
===
```

All options at the same level, in the same node, are presented at the same time. So the options we added here will be presented together. Lines indented after an option will only be run if that option is chosen.&#x20;

Any lines that are not options but occur _after_ options will only be run if one of the options does not jump away to another node.
{% endstep %}

{% step %}
## Play your Yarn Spinner Script yet again

Use the Run bhutton to once again run your script.&#x20;

You'll notice that when you choose the line `OK! Let's go!` the action will jump to the node entitle `Cave`. Great, right?
{% endstep %}
{% endstepper %}

### What did we just do?

We just wrote a simple Yarn Spinner script consisting of one **node** (titled `Start`), with one **line** inside that node, delivering a greeting from a narrator.&#x20;

Then we added two more nodes, a **jump command**, and some **options**, with jumps occuring depending on the option chosen.

And that's the very basics of Yarn Spinner Scripting! Dive into the [Fundamentals](write-yarn-scripts/syntax-basics/editing-with-vs-code/) of Writing Yarn Scripts next.

[^1]: This is called a **header**. This **header** is the **title**, and it’s always required in each node.

[^2]: This indicates the start of a node's content.

[^3]: This is a character name. Character names in Yarn Spinner are optional. If they exist, they're always at the beginning of a line, and consist of any text, followed by a colon.

[^4]: This indicates the end of a node.

[^5]: This is a jump command. All commands in Yarn Spinner are surrounded by `<<` and `>>`. The jump command contains the `jump` keyword, and then the title of the node you want to jump to. So, this particular jump command will jump to the node titled `Adventure`.
