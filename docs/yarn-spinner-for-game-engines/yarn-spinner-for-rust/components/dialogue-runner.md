# Dialogue Runner and a High Level Overview

The main way to actually manipulate the state of your dialog is through a `DialogueRunner`. You create it from a `YarnProject` (see [Compiling Yarn Files](../yarn-projects.md)) with either `YarnProject::create_dialogue_runner()` or `YarnProject::build_dialogue_runner()`. The first uses default configurations which should be alright for many use-cases, while the latter allows you to add or change functionality.

## Dialog Flow

The actual navigation through a dialog is handled by a [Dialogue View](dialogue-views.md), which is responsible for back-and-forth interaction with the player. As such, most of the methods provided by a `DialogueRunner` are to be called by such a view. The one you will want to call yourself, as seen in the [Quick Start](../quick-start.md), is `DialogueRunner::start_node`, which will tell the `DialogueRunner` to start running from the provided [node](../../../write-yarn-scripts/syntax-basics/lines-nodes-and-options.md).

## Variable Storage

[Variables](../../../write-yarn-scripts/syntax-basics/logic-and-variables.md) need to be stored in some place. By default, they are kept in memory through the `InMemoryVariableStorage`. This means that when you quit and reopen the game, all variables used in Yarn files will be empty again. Of course, this is suboptimal when you want to allow the player saving and loading their game state. To accomplish this, you can go one of two routes:

* Manipulate the variables in the variable store. Read then when saving and write them when loading. You can access the variable storage through `DialogueRunner::variable_storage()`.
* Directory use a variable storage that stores its variables in a persistent way, such as a database or a file. You can change the underlying variable storage through the builder API discussed later in this chapter.

For information on how to create your own variable storage, see the chapter [Variable Storage](variable-storage.md)

## Functions and Commands

Yarn files can contain user-defined functions and commands. These can be accessed with `DialogueRunner::library()` and `DialogueRunner::commands()`. For more information, see the chapters [Custom Functions](../creating-commands-functions/creating-functions.md) and [Custom Commands](../creating-commands-functions/creating-commands.md).

## Text and Assets

We make a distinction between _text_, which are the written words organized into _lines_ contained in Yarn files or in [localization files](../localisation.md), and _assets_, which are supplemental data associated with a line. Assets are referenced over a Bevy `Handle` and can be used for things such as voiceover sound files or images that might need translation.

Of note is that using assets **requires** using [localization](../localisation.md), or at least thinking about it. As a consequence, language settings are split between text and assets. After all, a player might want to hear lines delivered in the original recorded language but read the text translated into their own language.

You can read more about how current language can be set for a `DialogueRunner` in the [localization](../localisation.md) chapter.

Text is provided by a `TextProvider`. While it can be overwritten, the default `StringsFileTextProvider` will be a good choice for nearly all users. The only reason you might have to create an own `TextProvider` is if you want a very custom localization strategy, such as translating text automatically through AI.

Assets are provided by `AssetProvider`s. In contrast to the `TextProvider`, you might very well create your own `AssetProvider`. For your convenience, Yarn Spinner already ships with an `AudioAssetProvider` that you can use for voice lines and a `FileExtensionAssetProvider` that can load any asset based on naming conventions and file extensions. See the chapter [Assets](assets.md).

Text and asset providers can be set through the builder API and accessed later with `DialogueRunner::text_provider()` and `DialogueRunner::asset_providers()`. If you know the exact type `T` of `AssetProvider` you want, you can call `DialogueRunner::asset_provider::<T>()` instead.

## Builder API

As mentioned in the beginning of this chapter, a `DialogueRunner` can be modified or extended on creation by using `YarnProject::build_dialogue_runner()`. In fact, `YarnProject::create_dialogue_runner()` is nothing but a shorthand for `YarnProject::build_dialogue_runner().build()`.

You can use the builder API to inject your own implementations of traits used for the features presented in this chapter. `DialogueRunnerBuilder::with_variable_storage` changes the underlying `VariableStorage` and `DialogueRunnerBuilder::with_text_provider` the `TextProvider`. `DialogueRunnerBuilder::add_asset_provider` adds an `AssetProvider` to the set of asset providers called for each line presented to the player.
