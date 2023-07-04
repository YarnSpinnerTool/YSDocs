# Audio Line Provider

Audio Line Provider is a Line Provider that fetches localized text for a line of dialogue, as well as a localized AudioClip.

Audio Line Provider will automatically use Addressable Assets, if the Addressables package is installed in your Unity project and the [Yarn Project](../../importing-yarn-files/yarn-projects.md) is configured to use Addressable Assets.

{% hint style="info" %}
Use this Line Provider if you are using the [Built-In Localisation](../../assets-and-localization/inbuilt-localisation.md) system. If you are using the [Unity Localisation](../../assets-and-localization/unity-localization.md) system, use the [Unity Localised Line Provider](unity-localised-line-provider.md) instead.
{% endhint %}

### Inspector

|Property|Description|
|---|---|
|Text Language Code|The language that the Audio Line Provider should use to fetch localised text for.|
|Audio Language|The language that the Audio Line Provider should use to fetch localised audio clips for.|
