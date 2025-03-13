# In-built Localisation

This page covers what you need to know to use the internal localisation system built into Yarn Spinner. This supports both the localisation of the text, so the lines themselves, and your assets needed for them.

{% hint style="info" %}
The other option for localisation is to use the [Unity Localization package](unity-localization.md). The Unity Localisation package has more features, but is more complex.
{% endhint %}

Watch a video where Yarn Spinner developer Jon Manning walks you through using the Built-In Localisation System:

{% embed url="https://www.youtube.com/watch?v=d6qYQun0tfk" %}

## Set Up Localisations

When you want to prepare a Yarn Project for an additional language, you add a new Localisation in the Yarn Project.

Localisations are how you tell Yarn Spinner where to find the localised lines, and the localised line assets, for a given language.

To create a new Localisation, open the Localisations list in the Yarn Project's Inspector, and click the + button.

![The localisation settings for a project. The base language is English, and two localisations have been set up: one for English, and one for Russian.](../../.gitbook/assets/yarn-project-localisation.png)

Localisations have the following properties:

| Property      | Description                                                                                                                                                                          |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Language ID   | The language for this localisation.                                                                                                                                                  |
| Strings File  | A Text Asset containing the translated lines for this Yarn Project's scripts. See [Creating a Translation](./#creating-a-translation) for information on how to create these assets. |
| Assets Folder | A folder containing the localised assets for this localisation.                                                                                                                      |

{% hint style="info" %}
Your project always includes at least one localisation, which is for the base language.
{% endhint %}

## Creating a Translation

After you've set up a localisation, you can translate your dialogue into that localisation's language. To do this, you generate a _strings file_.

A strings file is a text-based spreadsheet, in [comma-separated value](https://en.wikipedia.org/wiki/Comma-separated_values) form, that contains a translated version of your dialogue. Yarn Spinner can generate a strings file for you, based on the [line IDs](./#adding-line-ids) in the dialogue.

{% hint style="info" %}
You don't need to create a strings file for your base localisation, because Yarn Spinner creates that for you by reading your source Yarn scripts. Any localisation whose language ID is the same as your base language will be marked as 'Automatically included'.
{% endhint %}

To create a strings file, select a Yarn Project, and click the "Export Strings and Metadata as CSV" button. Unity will ask where you want to save the strings file (the metadata file will have the same name as the strings file, but with a "-metadata" appended to it).

![A passage of Yarn script, next to the strings file for those lines.](../../.gitbook/assets/line-ids.png)

A strings file has the following structure:

| Column     | Description                                                                                                                                                                 |
| ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| language   | <p>The language code for this line.</p><p>When you export a strings file, this will be the Yarn project's base language.</p>                                                |
| id         | The line ID for this line.                                                                                                                                                  |
| text       | The text of the line, in the language indicated by the `language` column.                                                                                                   |
| file       | The file that the line was originally found in.                                                                                                                             |
| node       | The node that the line was originally found in.                                                                                                                             |
| lineNumber | The line number of the file that the line was originally found in.                                                                                                          |
| lock       | A unique value that Yarn Spinner uses to detect if the line has been modified since the strings file was generated. Don't modify or delete this value.                      |
| comment    | A note indicating the intent and tone of the line. This can be useful for translators who may not have the same background or context for how the line should be delivered. |

Once you've exported a strings file, you can translate it into another language: for each row in the database, change the `language` column to the new language you're translating into, and the `text` column to the translated text of the line.

{% hint style="warning" %}
Only the `language` and `text` columns should be modified by the translator. Don't modify the others; in particular, if you modify the value in the `id` column, Yarn Spinner won't be able to link the translated line to the original version.
{% endhint %}

The metadata file contains the `id`, `file`, `node`, and `lineNumber` columns (which have the same values as in the strings file). Additionally, it contains a `metadata` column with all the metadata of a line. Only lines that contain metadata will be present in this file. For more information on metadata, see [Tags and Metadata](../../using-yarnspinner-with-unity/assets-and-localization/getting-started/writing-in-yarn/tags-metadata.md).

{% hint style="info" %}
You can also provide the metadata file to the translator to give them more context and improve localisation accuracy.
{% endhint %}

Once you have a strings file that's been translated into your target language, you can add it to your Localisation. To do this, drag and drop the translated strings file into the Strings File property of your localisation, and click Apply.

{% hint style="info" %}
It's possible to update a strings file after you've made changes to your source scripts. For example, you might have added or removed lines, or made changes to the text.

To update a strings file, click the Update Existing Strings Files button at the bottom of the Inspector.

Yarn Spinner will update every strings file that's been added to the Localisations list: new lines will be added, removed lines will be deleted, and lines whose original text has changed since the last time the file was updated will have the text "NEEDS UPDATE" added to the end. This allows you to more easily find which lines need an updated translation.
{% endhint %}

## Adding Localised Assets

Localised line assets are assets that are associated with a particular line, in a particular localisation. The most common example of this is voice-over lines, which are audio assets that are associated with each line.

Line Providers are responsible for fetching the appropriate assets for a given line and language. For example, the [Audio Line Provider](../components/line-provider/audio-line-provider.md) fetches audio clips, and provides them to voice-over dialogue views.

## Selecting a Language at Run-time

The specific localised line, and localised line assets, that a line provider fetches depends on which language they have been configured to fetch.

The Text Line Provider has a single language option, which controls which language the line will appear in.

The Audio Line Provider has two language options: the language of the text, and the language of the audio files that are retrieved. This means that you can configure it to provide text in one language, and audio in another.

{% hint style="info" %}
If a line provider is asked to retrieve content for a language that it doesn't have any assets for, it will retrieve the base language version instead.
{% endhint %}
