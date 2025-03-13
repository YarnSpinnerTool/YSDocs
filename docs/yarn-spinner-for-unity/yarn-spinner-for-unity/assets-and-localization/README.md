# 🗺 Localisations and Assets

Localization is the process of translating and adapting content to a specific language, region or culture.

Yarn scripts are written in human-readable language. This is generally a single language, and (most of the time) will be written in the language that your development team primarily speaks. The language that a Yarn project is written in is called the _base language_.

However, if you want your dialogue to be understood by people who don't speak this language, you will need to translate it. Yarn Spinner is designed to make it easy to extract the user-facing text of your dialogue into a _strings file_, which can then be translated into a different language, and then loaded at run-time. You can translate your project into as many languages as you'd like, and Yarn Spinner will handle it for you automatically.

Yarn Spinner is also designed around the idea that a line of dialogue may have _assets_ associated with it. Most commonly, this means an audio file that contains an actor performing the line, so that it can be used in your game as a voice-over. These assets are also localisable.

{% hint style="info" %}
**I just want to add voiceover in a single language. Why do I need to localise, too?**

The philosophy of Yarn Spinner's approach to localisation is: if you want your dialogue to be text-only, and in a single language, you don't need to do anything at all. If you want to do anything else, you will need to set up a localisation and manage it using Yarn Spinner's processes.

We've found that most users who want to start using Yarn Spinner want to quickly get dialogue on the screen, and don't want to do lots of work to get the basics going. That's why we make the simple use-case (text only, a single language) as easy to use as we can.

However, if you're building a game that's voice acted, it makes your life significantly easier if you build your systems with localisation in mind from the start. Additionally, if you have the resources to add voice-over to your project, you should also have the resources to translate your game to other languages (even if you only have voice-overs in a single language.)

To that end, we designed it so that voiceover is intimately tied to localisation, so that you have to at least _start_ thinking about localisation at the start of the process.
{% endhint %}

## Localisation Terminology

* **Localisation**: A set of information that describes where to find text and assets for a given language.
* **Base language**: The language that your Yarn script files are written in.
* **Strings file**: A text document that contains translated versions of Yarn lines.
* **Line ID**: A unique code that identifies a line of dialogue or an option in the original source text.
* **Localised line**: The text of a line of dialogue, in a particular locale.
* **Localised line asset**: An asset (for example, an audio clip) that's associated for a particular line, in a particular locale. For example, an audio clip containing the voiceover for the line "Hello there", in German.
* **Line provider**: A [component](../components/line-provider/) that receives line IDs from the Dialogue Runner, and fetches the localised line and localised line assets (if present) for the player's preferred locale.

## Workflow

To localise your Yarn scripts, you specify the 'base language' that your scripts are written in. You then add unique _line ID_ tags to each line that identify each line. Finally, the localisation system reads your tagged lines and fills the string table for your base language. You can then add additional translations for your lines to the string tables for other languages.

### Writing Yarn Scripts

Every Yarn script is associated with a _base_ language. By default, Yarn Spinner sets the base language to that of your current locale. For example, if your computer is set to use Australian English, then Yarn Spinner will use that as the base language.

The base language of a Yarn Script is controlled by the [Yarn Project](../importing-yarn-files/yarn-projects.md) that it's a part of. You can change the language of your base localisation by changing the 'Base Language' setting on a Yarn Project.

### Adding Line IDs

In order to match different versions of a line, you need to add a _line id_ to each line of dialogue. A line ID is a tag that appears at the end of a line that uniquely identifies a line of dialogue in your game.

Here's an example of a line of dialogue with a line tag:

```
Gunther: I wanted orange! They gave me lemon-lime. #line:1a64a5
```

In this example, the line of dialogue has a line ID of `1a64a5`.

Yarn Spinner can add line IDs to your dialogue for you. To do this, select your Yarn Project, and click 'Add Line Tags to Scripts'. Yarn Spinner will re-write all of the script files, adding a line ID to any line that doesn't already have one.

{% hint style="info" %}
You can't generate a [strings file](inbuilt-localisation.md#creating-a-translation) unless all of the lines in all of the scripts in the Yarn Project have a line ID.
{% endhint %}

## Using Localised Content in Games

Once you've added line IDs to your Yarn scripts, they're ready to be used in your game's localisation system. Yarn Spinner works with the [Unity-provided Localization package](unity-localization.md), and can prepare your string tables and fetch content from those tables at run-time.

If you'd prefer to not use Unity's Localization package, Yarn Spinner also provides a built-in localisation system, which is described in [Built Yarn Spinner localisation system](inbuilt-localisation.md)
