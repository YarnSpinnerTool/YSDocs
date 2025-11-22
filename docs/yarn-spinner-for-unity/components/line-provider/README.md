# Line Provider

Line Providers are components that are responsible for taking the [Line](../../../api/csharp/yarn/line/) objects that the [Dialogue Runner](../dialogue-runner.md) produces, and fetches the appropriate localised content for that line. Line Providers produce [LocalizedLine](../../../api/csharp/yarn.unity/localizedline/) objects, which are sent to the Dialogue Runner's [Dialogue Presenters](../dialogue-view/).

When a Yarn Spinner Script runs, the Dialogue Runner produces Line objects. These objects contain information **about** the line, but not the text of the line itself. This is because it's the responsibility of the game to load the **user-facing** parts of the line, including the text of the line in the player's current language setting, as well as any other assets that may be needed to present the line, such as audio files for voiceover.

Yarn Spinner comes with two built-in types of line providers:

* [Built-In Localised Line Provider](built-in-localised-line-provider.md) is a Line Provider that uses Yarn Spinner's built-in localisation system.
* [Unity Localised Line provider](unity-localised-line-provider.md) is a Line Provider that fetches the text and any localised assets from [Unity's Localization system](../../assets-and-localization/unity-localization.md).

{% hint style="info" %}
If you don't set up a Line Provider for a Dialogue Runner, it will automatically create a Buit-In Localised Line Provider, and configure it to use the user's current language.
{% endhint %}
