# Line Provider

Line Providers are components that are responsible for taking the [Line](../../../api/csharp/yarn/line/README.md) objects that the [Dialogue Runner](../dialogue-runner.md) produces, and fetches the appropriate localised content for that line. Line Providers produce [LocalizedLine](../../../api/csharp/yarn.unity/localizedline/README.md) objects, which are sent to the Dialogue Runner's [Dialogue Views](../dialogue-view/README.md).

When a Yarn script runs, the Dialogue Runne produces Line objects. These objects contain information _about_ the line, but not the text of the line itself. This is because it's the responsibility of the game to load the _user-facing_ parts of the line, including the text of the line in the player's current language setting, as well as any other assets that may be needed to present the line (such as audio files for voiceover.)

Yarn Spinner comes with two built-in types of line providers:

* [Text Line Provider](text-line-provider.md) is a Line Provider that fetches the text of a line, given a language to use.
* [Audio Line Provider](audio-line-provider.md) is a Line Provider that fetches the text of a line as well as an [Audio Clip](https://docs.unity3d.com/ScriptReference/AudioClip.html), given languages to use.

{% hint style="info" %}
If you don't set up a Line Provider for a Dialogue Runner, it will automatically create a Text Line Provider, and configure it to use the user's current language.
{% endhint %}
