# Tags and Metadata

A _tag_ is a piece of information that you can add to content in Yarn Spinner that adds additional context or detail about that content.

There are two places you can add tags in Yarn scripts: you can add them to nodes, and you can add them to lines. Tags aren't shown to the user; instead, they're used by your game, or by Yarn Spinner itself.

## Tags in lines

Tags can be added to the end of lines and options. Tags on lines start with a *hash symbol* (`#`), and cannot contain spaces. You can add as many tags as you like to line, but they must all be on the same line in the script.

Here's an example of a line with two tags:

```
Homer: Hi, I'd like to order a tire balancing. #tone:sarcastic #duplicate
```

### Accessing tags

Tags that you add to a line can be accessed from your game. The way that you access them depends on your game engine. For example, to access them in a Unity game, you use the [LocalizedLine.Metadata](../../api/csharp/yarn.unity.localizedline.metadata.md) property.

Some tags are used by Yarn Spinner itself, while all others are used by your own code, so it's up to you what content they should have, and how to handle them.

### Special tags

Certain tags are used internally by Yarn Spinner, or are added for you if they don't exist.

#### `#lastline`

The Yarn Spinner compiler adds a `#lastline` tag to every line that comes just before a set of options.

For example, the following excerpt:

```
Hello there.
-> Hi!
-> What's up?
```

is treated as though it had been written as:

```
Hello there. #lastline
-> Hi!
-> What's up?
```

In a Unity game, you can use this tag in a custom [Dialogue View](../../using-yarnspinner-with-unity/components/dialogue-view/custom-dialogue-views.md) to be notified ahead of time when the player is about to be shown options.

{% hint style="info" %}
The `#lastline` tag will not be automatically added if there is any content, such as an `if` statement or a command, between the line and some options. In these situations, you may wish to manually add the tag yourself.
{% endhint %}

#### `#line`

The `#line` tag uniquely identifies a single line or option across all of your game's dialogue. This is used to identify lines for localisation. Every line's `#line` tag must be unique. If a line or option doesn't have a `#line` tag, it will be automatically added for you.

Here's an example of some Yarn script with `#line` tags:

```
Mechanic: You're in orbit of Jupiter, at a rest station along the main tourism lines. There's a meteorite headed towards here that'll completely destroy this station in three days. #line:4c49c5
Mechanic: And you're a wayfinding robot bolted to the floor of said Jupiter Tourist Station. #line:5b6256
-> Bolted to the floor?! #line:f65d07
	Mechanic: Yeah, like all tourist helper bots. #line:1b159b
-> Three days?! #line:40eaf7
	Mechanic: More or less. I wouldn't make any long-term plans. #line:3a6c94
```

For more details (including what the tag should look like), see [Adding Line IDs](using-yarnspinner-with-unity/assets-and-localization#adding-line-ids).

## Tags in nodes

Nodes can also have tags, which you can use to add labels that describe the node.

Node tags they work a bit differently than line tags: they are defined in the header with the `tags` key, and they don't have to begin with a hash symbol (`#`).

Here's an example of a node with two tags:

```
title: Train_Dialogue
tags: #camera2 background:conductor_cabin
---
Why did you stop the train?
Now we won't arrive in time at the next stop!
===
```

You can access the tags on a node via the Dialogue object's [GetTagsForNode](../../api/csharp/yarn.dialogue.gettagsfornode.md) method.

## Other metadata

The metadata of a line is only composed of tags. Because of this, you may find that the Yarn Spinner code and documentation refer to _line tags_ and _line metadata_ interchangeably.

Nodes can have other metadata in their headers. This metadata isn't exposed through the API, which means it's mostly used to store additional information for whoever is writing the Yarn dialogue or for editors to make use of.

However, currently there is one header that defines specific behavior within the Yarn Spinner compiler: the `tracking` header.

### The `tracking` header

Nodes can track whether they have already been visited during the game. For this to work, the Yarn Spinner compiler needs to add some special code to the node. To avoid creating this code for nodes that don't need it, the compiler only adds this code if it finds a call to the `visited()` function with the node name in it.

In some cases, you may need the compiler to add this special code to a node even if no corresponding `visited()` call exists. To direct the compiler to do this, include the `tracking` header with the value of `always`:

```
title: Node_Name
tracking: always
---
I know how many times you've been here.
===
```

Additionally, using a value of `never` instructs the compiler to _never_ add this special code to the node. If you use the `visited` function with a node set to never use tracking, it will always return `false`.

For more information on visit tracking, see the documentation for [Functions](functions.md).

## Example use cases

Tags and metadata may seem very complicated at first, and their uses may not be clear. The following example use cases explain how they can be used in your game. Keep in mind that this is not an exhaustive list of use cases.

### Controlling attributes for an entire line

Yarn provides [markup](./markup.md) to let you change attributes for specific parts of a line. In case most of your attributes apply to entire lines (for example, the color of a line), it may be easier to just use tags instead.

### Displaying the last line of dialogue along with options

The `#lastline` tag can be used to display the last line of dialogue along with any options. This is handled within your code by checking if a line has the `#lastline` tag, and if it does, storing it before continuing with the execution of the Yarn dialogue.

### Internal workflows

Since metadata isn't shown directly to the player, you can use metadata for any internal workflows or tooling. For example, instead of tracking lines that need to be revised outside the Yarn files (which could lead to syncing problems), you could add line tags (such as #needsrevision) to the appropriate lines directly in the Yarn files, and process these lines as part of an internal tool or workflow. The Unity integration automatically generates a CSV file with all lines that contain metadata, making this super easy!

### Localisation

As referenced before, the Yarn Spinner integration for Unity uses line tags to link localised dialogue lines. This is better explained in the [Localization and Assets](using-yarnspinner-with-unity/assets-and-localization/) section.

Aside from that, every piece of metadata can be used by translators and adapters to help them understand how the text is being used, thus leading to better localised text.

### Showing specific lines of dialogue outside a dialogue window

Some games may require that certain lines of dialogue are displayed somewhere other than the dialogue window (for example, as flavor text for an item description, or in an item that acts as a log). Instead of manually duplicating these lines (which adds overhead during development and localisation), tags can be used along with code that checks for the tags and duplicates the lines while the game is running.
