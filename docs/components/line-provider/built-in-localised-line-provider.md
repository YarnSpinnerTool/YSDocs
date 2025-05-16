# Built-in Localised Line Provider

The Built-in Localised Line Provider is a Line Provider that fetches localized text or audio assets (AudioClip) for a line of dialogue, given the user's language.&#x20;

The Built-in Localised Line Provider will automatically use Addressable Assets, if the Addressables package is installed in your Unity project and the [Yarn Project](../../yarn-spinner-for-unity/yarn-projects.md) is configured to use Addressable Assets.

{% hint style="info" %}
You'll automatically use this Line Provider if you are using the [Built-In Localisation](../../yarn-spinner-for-unity/assets-and-localization/inbuilt-localisation.md) system. If you are using the [Unity Localisation](../../yarn-spinner-for-unity/assets-and-localization/unity-localization.md) system, use the [Unity Localised Line Provider](unity-localised-line-provider.md) instead.
{% endhint %}

![A Built-in Localied Line Provider](<../../.gitbook/assets/Screenshot 2025-05-15 at 10.37.16 pm.png>)

### Inspector

| Property           | Description                                                                                           |
| ------------------ | ----------------------------------------------------------------------------------------------------- |
| Text Language Code | The language that the Built-in Localised Line Provider should use to fetch localised text for.        |
| Audio Language     | The language that the Built-in Localised Line Provider should use to fetch localised audio clips for. |
