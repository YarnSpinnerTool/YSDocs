# Tags and Metadata

Yarn Spinner allows **tags** in nodes and lines. These tags (along with a few other things) make up the **metadata** of a node or line, which are never shown directly to the player.

The primary purpose of metadata is to provide information to code that handles Yarn Spinner data and objects. Browse the [C# API](api/csharp) for the ways you can access this information from your code.

## Tags in lines

Tags are declared at the end of a line, and must always start with a *hash symbol* (#). With a few exceptions outlined in this page, they are mostly used by your own code, so it's up to you what content they should have, and how to handle them. Some example use cases are listed at the end of this page.

Here's an example of a line with two tags:

```
Homer: Hi, I'd like to order a tire balancing. #tone:sarcastic #duplicate
```

### The #lastline tag

The Yarn Spinner compiler adds a `#lastline` tag to every line that comes just before a set of options.

For example, the following excerpt:

```
Hello there.
-> Hi!
-> What's up?
```

Becomes:

```
Hello there. #lastline
-> Hi!
-> What's up?
```

### The #line tag

When working with localisations in the Yarn Spinner integration for Unity, lines require a special tag (called the *line id* tag), which is used to link together lines in every language. For more details (including what the tag should look like), see [this section](using-yarnspinner-with-unity/assets-and-localization#adding-line-ids) on the localisation page.

## Tags in nodes

Nodes can also have tags, although they work a bit differently than line tags: they are defined in the header with the `tags` key, and may or may not contain a *hash symbol* (#).

Here's an example of a node with two tags:

```
title: Train_Dialogue
tags: #camera2 background:conductor_cabin
---
Why did you stop the train?
Now we won't arrive in time at the next stop!
===
```

## Other metadata

The metadata of a line is only composed of tags. Because of this, you may find that the Yarn Spinner code and documentation refer to line tags and line metadata interchangeably.

Nodes can have other metadata in their headers. This metadata isn't exposed through the API (TODO: confirm this), which means it's mostly used to store additional information for whoever is writing the Yarn dialogue.

However, currently there is one header that defines specific behavior within the Yarn Spinner compiler: the `tracking` header.

### The tracking header

Nodes can track whether they have already been visited during the game. For this to work, the Yarn Spinner compiler needs to add some special code to the node. Since this behavior is not often needed, the compiler only adds this code if it finds a call to the `visited()` function with the node name in it.

In some cases, you may need the compiler to add this special code to a node even if no corresponding `visited()` call exists. To direct the compiler to do this, include the `tracking` header with the value of `always`:

```
title: Node_Name
tracking: always
---
I know how many times you've been here.
===
```

Additionally, using a value of `never` instructs the compiler to never add this special code to the node.

## Example use cases

Tags and metadata may seem very complicated at first, and their uses may not be clear. The following example use cases explain how they can be used in your game. Keep in mind that this is not an exhaustive list of use cases.

### Controlling attributes for an entire line

Yarn provides [markups](getting-started/writing-in-yarn/markup) to let you change attributes for specific parts of a line. In case most of your attributes apply to entire lines (for example, the color of a line), it may be easier to just use tags instead.

### Displaying the last line of dialogue along with options

The `#lastline` tag can be used to display the last line of dialogue along with any options. This is handled within your code by checking if a line has the `#lastline` tag, and if it does, storing it before continuing with the execution of the Yarn dialogue.

### Internal workflows

Since metadata isn't shown directly to the player, you can use metadata for any internal workflows or tooling. For example, instead of tracking lines that need to be revised outside the Yarn files (which could lead to syncing problems), you could add line tags (such as #needsrevision) to the appropriate lines directly in the Yarn files, and process these lines as part of an internal tool or workflow. The Unity integration automatically generates a CSV file with all lines that contain metadata, making this super easy!

### Localisation

As referenced before, the Yarn Spinner integration for Unity uses line tags to link localised dialogue lines. This is better explained in the [Localization and Assets](using-yarnspinner-with-unity/assets-and-localization) section.

Aside from that, every piece of metadata can be used by translators and adapters to help them understand how the text is being used, thus leading to better localised text.

### Showing specific lines of dialogue outside a dialogue window

Some games may require that certain lines of dialogue are displayed somewhere other than the dialogue window (for example, as flavor text for an item description, or in an item that acts as a log). Instead of manually duplicating these lines (which adds overhead during development and localisation), tags can be used along with code that checks for the tags and duplicates the lines while the game is running.