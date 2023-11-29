# Yarn.Unity Namespace

## Summary

Contains classes for working with Yarn Spinner in the Unity game engine.


## Attributes

|Name|Description|
|:---|:---|
|[YarnActionAttribute](/api/csharp/yarn.unity.yarnactionattribute.md)||
|[YarnParameterAttribute](/api/csharp/yarn.unity.yarnparameterattribute.md)|Yarn parameter.|
|[YarnStateInjectorAttribute](/api/csharp/yarn.unity.yarnstateinjectorattribute.md)|Inject state for any commands in this class using this static method.|

## Classes

|Name|Description|
|:---|:---|
|[Actions](/api/csharp/yarn.unity.actions.md)||
|[AudioLineProvider](/api/csharp/yarn.unity.audiolineprovider.md)||
|[CharacterColorView](/api/csharp/yarn.unity.charactercolorview.md)||
|[Cultures](/api/csharp/yarn.unity.cultures.md)|Provides access to all  <a href="yarn.unity.culture.md">Culture</a> s supported by Yarn Spinner.|
|[DialogueAdvanceInput](/api/csharp/yarn.unity.dialogueadvanceinput.md)|A component that listens for user input, and uses it to notify a dialogue view that the user wishes to advance to the next step in the dialogue.|
|[DialogueCharacterNameView](/api/csharp/yarn.unity.dialoguecharacternameview.md)|A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that displays character names.|
|[DialogueOption](/api/csharp/yarn.unity.dialogueoption.md)||
|[DialogueReference](/api/csharp/yarn.unity.dialoguereference.md)|Stores a reference to a dialogue node in a Yarn Project.|
|[DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)|The DialogueRunner component acts as the interface between your game and Yarn Spinner.|
|[DialogueViewBase](/api/csharp/yarn.unity.dialogueviewbase.md)|A  <code>UnityEngine.MonoBehaviour</code>  that can present lines and options to the user, when it receives them from a   <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .|
|[Effects](/api/csharp/yarn.unity.effects.md)|Contains coroutine methods that apply visual effects. This class is used by  <a href="yarn.unity.lineview.md">LineView</a>  to handle animating the presentation of lines.|
|[InMemoryVariableStorage](/api/csharp/yarn.unity.inmemoryvariablestorage.md)|A simple implementation of VariableStorageBehaviour.|
|[LanguageAttribute](/api/csharp/yarn.unity.languageattribute.md)||
|[LineMetadata](/api/csharp/yarn.unity.linemetadata.md)||
|[LineProviderBehaviour](/api/csharp/yarn.unity.lineproviderbehaviour.md)|A  <code>UnityEngine.MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.|
|[LineView](/api/csharp/yarn.unity.lineview.md)|A Dialogue View that presents lines of dialogue, using Unity UI elements.|
|[Localization](/api/csharp/yarn.unity.localization.md)||
|[LocalizedLine](/api/csharp/yarn.unity.localizedline.md)|Represents a line, ready to be presented to the user in the localisation they have specified.|
|[MarkupPalette](/api/csharp/yarn.unity.markuppalette.md)|Represents a collection of marker names and colours.|
|[OptionsListView](/api/csharp/yarn.unity.optionslistview.md)||
|[OptionView](/api/csharp/yarn.unity.optionview.md)||
|[SampleRenderDetector](/api/csharp/yarn.unity.samplerenderdetector.md)|Detects if the render pipeline is different from the one the samples were created with, and warn you that things might look odd.|
|[SerializedDictionary](/api/csharp/yarn.unity.serializeddictionary.md)|An  <code>System.Collections.Generic.IDictionary`2</code>  that can be serialized as part of a Unity object.|
|[TextLineProvider](/api/csharp/yarn.unity.textlineprovider.md)||
|[VariableStorageBehaviour](/api/csharp/yarn.unity.variablestoragebehaviour.md)|A  <code>UnityEngine.MonoBehaviour</code>  that a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  uses to store and retrieve variables.|
|[VoiceOverView](/api/csharp/yarn.unity.voiceoverview.md)|A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that plays voice-over  <code>UnityEngine.AudioClip</code> s for lines of dialogue.|
|[YarnCommandAttribute](/api/csharp/yarn.unity.yarncommandattribute.md)|An attribute that marks a method on an object as a command.|
|[YarnFunctionAttribute](/api/csharp/yarn.unity.yarnfunctionattribute.md)|Marks the method as a function to be registered with the running instance's library.|
|[YarnNodeAttribute](/api/csharp/yarn.unity.yarnnodeattribute.md)|Specifies that a field represents a reference to a named Yarn node that exists in a Yarn project.|
|[YarnProject](/api/csharp/yarn.unity.yarnproject.md)||

## Enums

|Name|Description|
|:---|:---|
|[LocalizationType](/api/csharp/yarn.unity.localizationtype.md)||

## Interfaces

|Name|Description|
|:---|:---|
|[IActionRegistration](/api/csharp/yarn.unity.iactionregistration.md)||
|[ICommand](/api/csharp/yarn.unity.icommand.md)||

## Namespaces

|Name|Description|
|:---|:---|
|[Yarn.Unity.UnityLocalization](/api/csharp/yarn.unity.unitylocalization.md)||

## Structs

|Name|Description|
|:---|:---|
|[Culture](/api/csharp/yarn.unity.culture.md)|Holds information about a language.|
|[StringTableEntry](/api/csharp/yarn.unity.stringtableentry.md)||

