# Yarn.Unity Namespace
Contains classes for using compiled Yarn programs in the Unity game engine.
## Classes
|Name|Description|
|:---|:---|
|[AddressableAudioLineProvider](/api/csharp/yarn.unity/addressableaudiolineprovider.md)||
|[AudioLineProvider](/api/csharp/yarn.unity/audiolineprovider.md)||
|[AudioLocalizedLine](/api/csharp/yarn.unity/audiolocalizedline.md)||
|[Cultures](/api/csharp/yarn.unity/cultures.md)| All [`Culture`](/api/csharp/yarn.unity/culture.md)s supported by YarnSpinner. |
|[DeclarationPropertyDrawer](/api/csharp/yarn.unity/declarationpropertydrawer.md)||
|[DialogueCharacterNameView](/api/csharp/yarn.unity/dialoguecharacternameview.md)| A subclass of [`DialogueViewBase`](/api/csharp/yarn.unity/dialogueviewbase.md) that displays character names. |
|[DialogueOption](/api/csharp/yarn.unity/dialogueoption.md)||
|[DialogueRunner](/api/csharp/yarn.unity/dialoguerunner.md)| The [DialogueRunner]({{<ref "/docs/unity/components/dialogue-runner.md">}}) component acts as the interface between your game and Yarn Spinner. |
|[DialogueRunner.StringUnityEvent](/api/csharp/yarn.unity/dialoguerunner.stringunityevent.md)| A type of <see cref="!:UnityEvent"></see> that takes a single string parameter.  |
|[DialogueUI](/api/csharp/yarn.unity/dialogueui.md)| Displays dialogue lines to the player, and sends user choices back to the dialogue system. |
|[DialogueViewBase](/api/csharp/yarn.unity/dialogueviewbase.md)| A <see cref="!:MonoBehaviour"></see> that can present the data of a dialogue executed by a [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) to the user. The [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) uses subclasses of this type to relay information to and from the user, and to pause and resume the execution of the <see cref="!:YarnScript"></see>. |
|[InMemoryVariableStorage](/api/csharp/yarn.unity/inmemoryvariablestorage.md)| A simple implementation of VariableStorageBehaviour. |
|[InMemoryVariableStorageEditor](/api/csharp/yarn.unity/inmemoryvariablestorageeditor.md)||
|[LineProviderBehaviour](/api/csharp/yarn.unity/lineproviderbehaviour.md)| A <see cref="!:MonoBehaviour"></see> that produces [`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md)s. |
|[Localization](/api/csharp/yarn.unity/localization.md)||
|[LocalizationDatabase](/api/csharp/yarn.unity/localizationdatabase.md)||
|[LocalizationDatabaseEditor](/api/csharp/yarn.unity/localizationdatabaseeditor.md)||
|[LocalizedLine](/api/csharp/yarn.unity/localizedline.md)| Represents a line, ready to be presented to the user in the localisation they have specified. |
|[Preferences](/api/csharp/yarn.unity/preferences.md)| Yarn preferences made by the user that should not be stored in a project or in a build. |
|[ReorderableDeclarationsList](/api/csharp/yarn.unity/reorderabledeclarationslist.md)||
|[SerializedDictionary<TKey, TValue>](/api/csharp/yarn.unity/serializeddictionary-2.md)| An <see cref="!:IDictionary<TKey,TValue>"></see> that can be serialized as part of a Unity object. |
|[TextLineProvider](/api/csharp/yarn.unity/textlineprovider.md)||
|[VariableStorageBehaviour](/api/csharp/yarn.unity/variablestoragebehaviour.md)| A <see cref="!:MonoBehaviour"></see> that a [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md) uses to store and retrieve variables. |
|[VoiceOverPlaybackUnity](/api/csharp/yarn.unity/voiceoverplaybackunity.md)| Handles playback of voice over <see cref="!:AudioClip"></see>s referenced on <see cref="!:YarnScript"></see>s. |
|[YarnCommandAttribute](/api/csharp/yarn.unity/yarncommandattribute.md)| An attribute that marks a method on a <see cref="!:MonoBehaviour"></see> as a [command]( {{<ref "/docs/unity/working-with-commands">}}). |
|[YarnImporter](/api/csharp/yarn.unity/yarnimporter.md)| A <see cref="!:ScriptedImporter"></see> for Yarn assets. The actual asset used and referenced at runtime and in the editor will be a <see cref="!:YarnScript"></see>, which this class wraps around creating the asset's corresponding meta file. |
|[YarnLinesAsCanvasText](/api/csharp/yarn.unity/yarnlinesascanvastext.md)| Shows Yarn lines on Canvas Text components. |
|[YarnLinesAsCanvasText.StringObjectDictionary](/api/csharp/yarn.unity/yarnlinesascanvastext.stringobjectdictionary.md)||
|[YarnLinesAsCanvasTextEditor](/api/csharp/yarn.unity/yarnlinesascanvastexteditor.md)||
|[YarnProgram](/api/csharp/yarn.unity/yarnprogram.md)||
|[YarnProgramImporter](/api/csharp/yarn.unity/yarnprogramimporter.md)||
|[YarnProgramImporter.SerializedDeclaration](/api/csharp/yarn.unity/yarnprogramimporter.serializeddeclaration.md)||
|[YarnProgramImporterEditor](/api/csharp/yarn.unity/yarnprogramimportereditor.md)||
|[YarnSpinnerEditorWindow](/api/csharp/yarn.unity/yarnspinnereditorwindow.md)||
|[YarnTranslation](/api/csharp/yarn.unity/yarntranslation.md)| Maps a language ID to a TextAsset. |
## Structs
|Name|Description|
|:---|:---|
|[Culture](/api/csharp/yarn.unity/culture.md)| Holds information about a language. |
|[StringTableEntry](/api/csharp/yarn.unity/stringtableentry.md)||
## Enums
|Name|Description|
|:---|:---|
|[LineStatus](/api/csharp/yarn.unity/linestatus.md)| The presentation status of a [`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md). |
