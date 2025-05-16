# Unity Localised Line Provider

Unity Localised Line Provider is a Line Provider that fetches localized text and assets for a line of dialogue from a String Table and optionally from an Asset Table, based on the project's current localization settings.

{% hint style="info" %}
Use this Line Provider if you are using the [Unity Localisation](../../assets-and-localization/unity-localization.md) system. If you are using the [Built-In Localisation](../../assets-and-localization/inbuilt-localisation.md) system, use the [Text Line Provider](broken-reference) or the [Audio Line Provider](broken-reference) instead.
{% endhint %}

### Inspector

| Property      | Description                                                                                                                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Strings Table | The String Table Collection containing localised line text. See [Unity Localization](../../assets-and-localization/unity-localization.md) to learn how to populate it with your project's dialogue.           |
| Assets Table  | _(Optional)_ The Asset Table Collection containing localised assets. If an Asset Table is provided, then the Unity Localised Line Provider will fetch localised assets for each line, based on the line's ID. |
