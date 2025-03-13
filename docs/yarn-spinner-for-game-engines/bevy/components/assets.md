# Assets

While Bevy as a whole has assets, Yarn Spinner can associate specific assets with lines. These are always [localised](../localisation.md), such as voiceovers.

## Using Metadata Instead of Assets

Before we jump into assets, let's first help you out if you don't care about localization. The mechanism in place for this is _line metadata_, which are strings you can add to Yarn lines after a hashtag:

```
title: Start
---
Granny: It's hard to believe that it's over, isn't it? #smiling
Granny: Funny how we get attached to the struggle. #laughing
Granny: Promise me that you'll take care of yourself, okay? #smiling
===
```

A [Dialogue View](dialogue-views.md) will be able to read the metadata "smiling", "laughing", and "smiling" again from `LocalizedLine::metadata` and accordingly load things like character portraits. These annotations will also be written into the "comment" field of strings files, which are explained in the chapter [Localisation](../localisation.md).

## Asset Providers

Assets are fetched from the filesystem by structs implementing `AssetProvider`. They need to be registered when creating a `DialogueRunner`. For example, if you use the `audio_assets` feature, you can register an asset provider for audio files by modifying the code found in the [Quick Start](../quick-start.md) like this:

```rust
fn spawn_dialogue_runner(mut commands: Commands, project: Res<YarnProject>) {
    let mut dialogue_runner = project
        .build_dialogue_runner()
        .add_asset_provider(AudioAssetProvider::new())
        .build();
    dialogue_runner.start_node("Start");
    commands.spawn(dialogue_runner);
}
```

{% hint style="warning" %}
The bundled example Dialogue View does not play any audio files, so you will need to write your own [Dialogue View](dialogue-views.md) to make use of this feature.
{% endhint %}

The `AudioAssetProvider` itself is just a specialized [`FileExtensionAssetProvider`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/default_impl/struct.FileExtensionAssetProvider.html). As the name suggests, it serves any assets based on their extension:

```rust
fn spawn_dialogue_runner(mut commands: Commands, project: Res<YarnProject>) {
    let image_provider = FileExtensionAssetProvider::new()
        .with_file_extensions(file_extensions! {
           Image: ["png", "jpg", "jpeg"],
        });
    let mut dialogue_runner = project
        .build_dialogue_runner()
        .add_asset_provider(image_provider)
        .build();
    dialogue_runner.start_node("Start");
    commands.spawn(dialogue_runner);
}
```

The [`FileExtensionAssetProvider`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/default_impl/struct.FileExtensionAssetProvider.html) (and, by extension, the `AudioAssetProvider`) will search for their assets in the directory `assets/dialogue/<language>/<line-id.extension>`. So, for example, an `AudioAssetProvider` serving up a voiceover for the line with the ID 41239 while the game is set to the language "de-CH" will search for `assets/dialogue/de-CH/41239.mp3`.

Finally, you can implement [`AssetProvider`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/trait.AssetProvider.html) yourself with whatever custom behavior you desire. Check out the trait's documentation for the necessary methods.
