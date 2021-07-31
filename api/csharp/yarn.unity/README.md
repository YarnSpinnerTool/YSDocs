# Yarn.Unity Namespace

Contains classes for using compiled Yarn programs in the Unity game engine.

## Classes

| Name | Description |
| :--- | :--- |
| [`AddressableAudioLineProvider`](addressableaudiolineprovider/) |  |
| [`AudioLineProvider`](audiolineprovider/) |  |
| [`AudioLocalizedLine`](audiolocalizedline/) |  |
| [`Cultures`](cultures/) | All [`Culture`](culture/)s supported by YarnSpinner. |
| [`DeclarationPropertyDrawer`](declarationpropertydrawer/) |  |
| [`DialogueCharacterNameView`](dialoguecharacternameview/) | A subclass of [`DialogueViewBase`](dialogueviewbase/) that displays character names. |
| [`DialogueOption`](dialogueoption/) |  |
| [`DialogueRunner`](dialoguerunner/) | The \[DialogueRunner\]\(\) component acts as the interface between your game and Yarn Spinner. |
| [`DialogueRunner.StringUnityEvent`](dialoguerunner.stringunityevent.md) | A type of  that takes a single string parameter. |
| [`DialogueUI`](dialogueui/) | Displays dialogue lines to the player, and sends user choices back to the dialogue system. |
| [`DialogueViewBase`](dialogueviewbase/) | A  that can present the data of a dialogue executed by a [`DialogueRunner`](dialoguerunner/) to the user. The [`DialogueRunner`](dialoguerunner/) uses subclasses of this type to relay information to and from the user, and to pause and resume the execution of the . |
| [`InMemoryVariableStorage`](inmemoryvariablestorage/) | A simple implementation of VariableStorageBehaviour. |
| [`InMemoryVariableStorageEditor`](inmemoryvariablestorageeditor/) |  |
| [`LineProviderBehaviour`](lineproviderbehaviour/) | A  that produces [`LocalizedLine`](localizedline/)s. |
| [`Localization`](localization/) |  |
| [`LocalizationDatabase`](localizationdatabase/) |  |
| [`LocalizationDatabaseEditor`](localizationdatabaseeditor/) |  |
| [`LocalizedLine`](localizedline/) | Represents a line, ready to be presented to the user in the localisation they have specified. |
| [`Preferences`](preferences/) | Yarn preferences made by the user that should not be stored in a project or in a build. |
| [`ReorderableDeclarationsList`](reorderabledeclarationslist/) |  |
| [`SerializedDictionary<TKey, TValue>`](serializeddictionary-2/) | An  that can be serialized as part of a Unity object. |
| [`TextLineProvider`](textlineprovider/) |  |
| [`VariableStorageBehaviour`](variablestoragebehaviour/) | A  that a [`DialogueRunner`](dialoguerunner/) uses to store and retrieve variables. |
| [`VoiceOverPlaybackUnity`](voiceoverplaybackunity/) | Handles playback of voice over s referenced on s. |
| [`YarnCommandAttribute`](yarncommandattribute/) | An attribute that marks a method on a  as a \[command\]\( \). |
| [`YarnImporter`](yarnimporter/) | A  for Yarn assets. The actual asset used and referenced at runtime and in the editor will be a , which this class wraps around creating the asset's corresponding meta file. |
| [`YarnLinesAsCanvasText`](yarnlinesascanvastext/) | Shows Yarn lines on Canvas Text components. |
| [`YarnLinesAsCanvasText.StringObjectDictionary`](yarnlinesascanvastext.stringobjectdictionary.md) |  |
| [`YarnLinesAsCanvasTextEditor`](yarnlinesascanvastexteditor/) |  |
| [`YarnProgram`](yarnprogram/) |  |
| [`YarnProgramImporter`](yarnprogramimporter/) |  |
| [`YarnProgramImporter.SerializedDeclaration`](yarnprogramimporter.serializeddeclaration/) |  |
| [`YarnProgramImporterEditor`](yarnprogramimportereditor/) |  |
| [`YarnSpinnerEditorWindow`](yarnspinnereditorwindow.md) |  |
| [`YarnTranslation`](yarntranslation/) | Maps a language ID to a TextAsset. |

## Structs

| Name | Description |
| :--- | :--- |
| [`Culture`](culture/) | Holds information about a language. |
| [`StringTableEntry`](stringtableentry/) |  |

## Enums

| Name | Description |
| :--- | :--- |
| [`LineStatus`](linestatus/) | The presentation status of a [`LocalizedLine`](localizedline/). |

