# Adding Localizations and Assets to Projects

Localization is the process of translating and adapting content to a specific language, region or culture. 

Yarn scripts are written in human-readable language. This is generally a single language, and (most of the time) will be written in the language that your development team primarily speaks. The language that a Yarn project is written in is called the _base language_.

However, if you want your dialogue to be understood by people who don't speak this language, you will need to translate it. Yarn Spinner is designed to make it easy to extract the user-facing text of your dialogue into a _strings file_, which can then be translated into a different language, and then loaded at run-time. You can translate your project into as many languages as you'd like, and Yarn Spinner will handle it for you automatically.

Yarn Spinner is also designed around the idea that a line of dialogue may have _assets_ associated with it. Most commonly, this means an audio file that contains an actor performing the line, so that it can be used in your game as a voice-over. These assets are also localisable.

{% hint style="info" title="I just want to add voiceover. Why do I need to localise?" %}
The philosophy of Yarn Spinner's approach to localisation is: if you want your dialogue to be text-only and in a single language, you don't need to do anything at all. If you want to do anything else, you will need to set up a localisation and manage it using Yarn Spinner's processes.

The idea behind this is that if you're building a game that's voice acted, it makes your life significantly easier if you build your systems with localisation in mind from the start. Additionally, if you have the resources to add voice-over to your project, you should also have the resources to translate your game to other languages (even if you only have voice-overs in a single language.)

To that end, we designed it so that voiceover is intimately tied to localisation, so that you have to at least _start_ thinking about localisation at the start of the process.
{% endhint %}

In Yarn Spinner, the localisation workflow works like this:

1. Write your Yarn scripts in your base language.
2. Set up localisations in the Yarn Project for each of the languages you wish to support. (This includes your base language.)
3. For each localisation besides your base language:
   1. Export a strings file.
   2. Translate its contents into another language.
   3. Associate the strings file with the localisation.
4. If you have assets you want to use with your dialogue, associate the folder that contains those assets with the localisation they belong to.
5. During gameplay, set your [Line Provider](../components/line-provider/README.md)'s language to the user's preferred language.

In the following sections, we'll go through each of these steps.

## Writing Yarn Scripts

TODO

## Set Up Localisations

TODO

## Creating a Translation

TODO

## Adding Localised Assets

TODO

## Selecting a Language at Run-time

TODO
