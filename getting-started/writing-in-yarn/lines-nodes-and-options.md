# Nodes, Lines, and Options

In Yarn Spinner, all of your dialogue is stored in `.yarn` files. Yarn files are just plain text files, which you can edit in any text editor.

## Nodes

Yarn Spinner files contain **nodes**. Nodes are where you put your dialogue. You can have as many nodes as you link in a file. Nodes are used to separate out parts of the story, and make it easier to manage longer stories and branching.

Each node has, at the very minimum, a collection of **headers,** and a **body**. All nodes have at least one header, which is the **title**. The title is the name of the node, and the body contains the Yarn script that contains your game's dialogue.

The title of a node is important, because your game uses node titles to tell Yarn Spinner which node to start running. You also use the title of a node when you want to jump to another node.

Node titles are not shown to the player.

{% hint style="warning" %}
Node titles must start with a letter, and can contain letters, numbers and underscores.

So **FirstNode**, **First**\_**Node** and **Node1** valid, but **First Node** and **1stNode** are not.&#x20;
{% endhint %}

{% hint style="danger" %}
Node names cannot contain a `. (period).`Node names were able to contain a period in Yarn Spinner 1, and if your Yarn Spinner 1 `.yarn` scripts have periods in the node names, you can use the [upgrader script](../upgrading-yarn-scripts.md) to convert them (and all jumps and options related) to use a `_` (underscore) instead.
{% endhint %}

### Writing Nodes in Plain Text

If you're using a text editor to write Yarn scripts, you'll need to write the node's header.

{% hint style="info" %}
If you're using a graphical editor to write Yarn scripts, like _Yarn Editor_, it will handle this for you, and you can skip this section.
{% endhint %}

The plain-text version of a Yarn node looks like this:

```
title: Node_Title
---
Here are some lines!
Wow!
===
```

In this example, the node's title is `Node_Title`, which is set on the first line in the `title` header. You can also add any other headers that you want.

{% hint style="info" %}
Node headers can contain any number of lines with the structure **`key: value`**. This can be used to store additional information, such as the location the conversation is taking place.
{% endhint %}

The `---` marker indicates where the body begins. After this point, you can put all of your Yarn script.

The `===` marker indicates where the node ends; after this point, you can begin another node.

## Node Content

The body of a node is made up of three different kinds of content: _lines_, _commands_, and _options_.

### Lines

When you write Yarn Spinner dialogue, just about every line of text that you write in a node is a **line**. When a node is run, it runs each line, one at a time, and sends it to your game.

A line of dialogue is just the thing you want some entity or character to say, usually beginning with the name of the entity speaking.

For example, consider the following Yarn code from _Night in the Woods_:

```
Mae: Well, this is great.
Mae: I mean I didn't expect a party or anything
Mae: but I figured *someone* would be here.
Mae: ...
Mae: Welcome home, Mae.
```

When this code is run in the game, it looks like this:

![Lines of dialogue running in Night in the Woods.](../../.gitbook/assets/lines.gif)

Yarn Spinner sends each of these lines, one at a time, to the game. The game is responsible for taking the text, and presenting it to the player; in the case of _Night in the Woods_, this means drawing the speech bubble, animating each letter in, and waiting for the user to press a key to advance to the next line.

Lines of dialogue can contain just about any text, except for some special characters that Yarn Spinner uses to add extra information to a line.

If there is a set of characters without spaces before a colon (:) at the beginning of the line, Yarn Spinner will mark that as the name of the character. This information will then be passed to your game, so that you can change the way that lines are shown based on the character who's saying them. For example:

```
This is a line of dialogue, without a character name.
Speaker: This is another line of dialogue said by a character called "Speaker".
```

### Options

When you want to let the player decide what to say, you use an **option**. Options let you show multiple potential lines of dialogue to the player, and let the player select one.

Options are marked with a `->` symbol. You write as many options as you'd like the player to see, and the player chooses one of them. The content of the option is like any other line of dialogue.

For example, consider the following code:

```
Companion: Hi there! What do you feel like doing today?

-> Player: I want to go swimming.
-> Player: I'd prefer to go hiking.
```

In this example, the line "Hi there! What do you feel like doing today?" will run. The player will then be given the choice to say either "I want to go swimming", or "I'd prefer to go hiking".

#### Options and Lines

Shortcut options can have their own lines, which are run when the option is selected. If a different option is selected, they won't run. To write this, _indent_ the lines that belong to a shortcut option.

In the following code, different lines will run based on which of the two shortcut options are selected.

```
Companion: Hi there! What do you feel like doing today?

-> Player: I want to go swimming.
    Companion: Okay, let's go swimming.
-> Player: I'd prefer to go hiking.
    Companion: Cool, we'll go hiking then.
    
Player: Sounds good!
```

This script will start with the line, "Hi there! What do you feel like doing today?". The player then has the choice of saying either "I want to go swimming", or "I'd prefer to go hiking". Depending on their choice, either the line "Okay, let's go swimming" or "Cool, we'll go hiking then". Finally, no matter what was selected, the line "Sounds good!" will run.

#### Nested Options

In addition to containing lines, options can also contain _other_ options.

```
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
```

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

Separating dialogue segments into nodes can make for neater files that are easier to edit as they grow.

Sometimes it makes sense for the options presented or the outcomes of selecting different options to vary based on other things the player has done or said up until this point. This requires the use of **logic** and **variables**, which we'll discuss in the next section.
