---
description: >-
  The second step in our three-party beginner's guide to Yarn Spinner: writing
  Yarn scripts using the Yarn Spinner for Visual Studio Code Extension.
---

# 📖 Writing Narratives

## Installing Visual Studio Code

To use Yarn Spinner for Visual Studio Code, you’ll first need to install Visual Studio Code.

First, **download Visual Studio Code from the official website:** [**https://code.visualstudio.com**](https://code.visualstudio.com)

Once it’s downloaded, install it, and open it up. Choose the **View menu → Extensions**, to open the **Extensions Marketplace**:

In the Extensions Marketplace, search for “Yarn Spinner”, and install the extension provided by **Secret Lab**:

Install Yarn Spinner for Visual Studio Code.

## Using Yarn Spinner for Visual Studio Code

Create a new, empty file in Visual Studio Code (VS Code), and add something like the following to it (it’s just the Party example, from the end of the previous step):

```yaml
title: Party
---
<<declare $partyHats = 0>>
Partygoer A: We're having a party!
Partygoer B: Yeah, we are!
Partygoer A: Want a party hat?
    -> Yes, please!
        <<set $partyHats = $partyHats + 1>>
        Partygoer A: Here you go!
        Partygoer B: Look over here!
            <<jump OverHere>>
    -> No, thanks. I despise happiness. I relish misery.
        Partygoer A: We see that.
        Partygoer B: Why don't you go over there?
            <<jump OverThere>>
    -> I'd rather go over here...
        <<jump OverThere>>
===

title: OverHere
---
Partygoer C: Oh hi. Can I borrow a party hat? 
Partygoer C: I lost mine.
<<if $partyHats > 0>>
    Partygoer C: Looks like you can spare a hat.
        -> Sure, here you go.
            <<set $partyHats = $partyHats - 1>>
            <<jump OverThere>>
        -> No. Never. Absolutely not.
            <<jump OverThere>>
<<else>>
    Partygoer C: Oh, you don't have any to spare.
    Partygoer C: Cya around, I guess.
    <<jump Party>>
<<endif>>
===

title: OverThere
---
Partygoer D: Hi!
<<if $partyHats > 0 and $partyHats <= 2>>
    Partygoer D: You're definitely fun.
        -> Why?
            Partygoer D: You like party hats.
                -> Thanks! You're fun too.
                    <<jump Party>>
<<elseif $partyHats > 2>>
    Partygoer D: You have too many hats!
    Partygoer D: It really scares me.
        -> Sorry...
            <<jump Party>>
<<else>>
    Partygoer D: You should go party somewhere else in this party.
        -> Oh, bye, then...
            <<jump Party>>
<<endif>>
===
```

Save the file somewhere sensible as `TestYarn1.yarn` (the filename is not important, but the `.yarn` extension is).

With the new file open, look at the bottom right-hand corner of the VSCode window, and verify that the file is recognised as a Yarn Spinner file:

Yarn Spinner for Visual Studio Code allows you to do a whole bunch of useful things in VSCode, including. Let’s take a look at some of them.

### Syntax highlighting

The most obvious immediate feature is that Yarn’s syntax will be appropriately identified and highlighted in the editor. Very useful. You can see this in action in your `TestYarn1.yarn` file, showing the Party example.

But, so far, this is pretty similar to the features of Try Yarn Spinner. Let’s go deeper.

Play around with the Graph View.

### Graph view

Press the Show Graph button in the top right-hand corner of the window, or open the Command Palette and choose Yarn Spinner: Show Graph.

You’ll be stunned, amazed, and totally overwhelmed by what happens next. A graph view, showing your nodes from the open yarn script will appear!

\<aside> 💡 We’re not here to teach you VSCode, but one thing that’s important to point out is the **Command Palette.**You can access it by pressing Command+Shift+P or Control+Shift+P on your keyboard:

The Command Palette allows you to type a few characters to filter by all the commands available in VSCode. With Yarn Spinner for Visual Studio Code installed, you’ll have access to a collection of Yarn Spinner-related commands:

**Preview Dialogue** will open a playable preview of your dialogue inside VSCode:

**Show Graph** will open the same graph view, showing your nodes, as the Show Graph button does.

The three **Export Dialogue as…** commands will, unsurprisingly, allow you to export your dialogue in a variety of different formats. These are mostly outside the scope of this workshop, however **Export Dialogue as HTML…** will give you an entirely self-contained HTML copy of the playable preview of your yarn script. Fun!

Open the Command Palette and find the Yarn Spinner commands.

### Yarn script awareness

Yarn Spinner for Visual Studio code has a few other tricks up its sleeve when it comes to making your Yarn script writing experience better.

For example, if you add a comment using the triple slash `///` you can describe what a variable is for, and Yarn Spinner for Visual Studio will display this description whenever you hover over a variable.

So, if you add a `///` comment above the declaration of `$partyHats`, like this:

```csharp
/// Counts the number of Party Hats that the player has. Starts at 0.
<<declare $partyHats = 0>>
```

You’ll then be able to hover over `$partyHats` and see the description, like this:

You can also hold Command (on macOS) or Control (on Windows and Linux) and click on the name of a node (for example inside a `<<jump>>` statement), and the editor will jump to that node. You can also do this from the Graph View.

You can also use Yarn Spinner for Visual Studio Code to easily find out what references a node, by looking above each node’s header. The amount of references to that node will be shown, as well as a shortcut to jump to that node in the Graph View:

Clicking the references will show you all the references to that node:

#### Improving the graph view

The Graph View is useful out of the box, but with a few tweaks to your Yarn scripts you can make it even more effective.

For example, you can assign a colour to nodes by adding a `color` header, like so:

```csharp
title: Party
color: red
---
// the node's content is here
===
```

Then, your node will have a colour indicator:

You can also put nodes in groups by adding a `group` header, like so:

```csharp
title: Party
color: red
group: main
---
// this node's content is here
===

title: OverHere
color: green
group: other_places
---
// this node's content is here
===

title: OverThere
color: purple
group: other_places
---
// this node's content is here
===
```

Then, your nodes will be visually grouped in the Graph View:

Neither the colour nor the group will have any impact on your game’s use of the dialogue. It’s just for ease-of-use of the Graph View.

You can also use the `tags` header, with a space-separated list of tags. This doesn’t impact anything in the editor, but is available to be queried from Yarn Spinner within Unity, for you to do what you want with.

## Writing a story

Take what you’ve learned so far, and write a story that makes use of:

* nodes
* `jump` statements
* variables
* `if` statements (and `elseif`)
* setting variables
* options, nested options, and conditional options
* built-in functions

… and is **nicely** laid out in Yarn Spinner for Visual Studio Code, with groups, colours, and a nicely presented Graph View.

You story should be playable using the Preview feature of Yarn Spinner for Visual Studio Code, accessible via the Command Palette.
