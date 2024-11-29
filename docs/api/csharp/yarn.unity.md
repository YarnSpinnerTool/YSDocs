# Yarn.Unity Namespace

## Summary

Contains classes for working with Yarn Spinner in the Unity game engine.


## Attributes

|Name|Description|
|:---|:---|
|[YarnActionAttribute](/docs/api/csharp/yarn.unity.yarnactionattribute.md)||
|[YarnEditorAttribute](/docs/api/csharp/yarn.unity.yarneditorattribute.md)||
|[YarnParameterAttribute](/docs/api/csharp/yarn.unity.yarnparameterattribute.md)|Yarn parameter.|
|[YarnStateInjectorAttribute](/docs/api/csharp/yarn.unity.yarnstateinjectorattribute.md)|Inject state for any commands in this class using this static method.|

## Classes

|Name|Description|
|:---|:---|
|[ActionRegistrationExtension](/docs/api/csharp/yarn.unity.actionregistrationextension.md)||
|[Actions](/docs/api/csharp/yarn.unity.actions.md)||
|[AsyncDialogueViewBase](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)||
|[BuiltinLocalisedLineProvider](/docs/api/csharp/yarn.unity.builtinlocalisedlineprovider.md)||
|[CharacterColorView](/docs/api/csharp/yarn.unity.charactercolorview.md)||
|[Cultures](/docs/api/csharp/yarn.unity.cultures.md)|Provides access to all  <a href="yarn.unity.culture.md">Culture</a> s supported by Yarn Spinner.|
|[DialogueAdvanceInput](/docs/api/csharp/yarn.unity.dialogueadvanceinput.md)|A component that listens for user input, and uses it to notify a dialogue view that the user wishes to advance to the next step in the dialogue.|
|[DialogueCharacterNameView](/docs/api/csharp/yarn.unity.dialoguecharacternameview.md)|A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that displays character names.|
|[DialogueOption](/docs/api/csharp/yarn.unity.dialogueoption.md)||
|[DialogueReference](/docs/api/csharp/yarn.unity.dialoguereference.md)|Stores a reference to a dialogue node in a Yarn Project.|
|[DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)||
|[DialogueViewBase](/docs/api/csharp/yarn.unity.dialogueviewbase.md)|A  <code>UnityEngine.MonoBehaviour</code>  that can present lines and options to the user, when it receives them from a   <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .|
|[Effects](/docs/api/csharp/yarn.unity.effects.md)|Contains coroutine methods that apply visual effects. This class is used by  <a href="yarn.unity.lineview.md">LineView</a>  to handle animating the presentation of lines.|
|[GeneratedVariableStorageExtensions](/docs/api/csharp/yarn.unity.generatedvariablestorageextensions.md)||
|[GroupAttribute](/docs/api/csharp/yarn.unity.groupattribute.md)||
|[HideIfAttribute](/docs/api/csharp/yarn.unity.hideifattribute.md)||
|[IndentAttribute](/docs/api/csharp/yarn.unity.indentattribute.md)||
|[InMemoryVariableStorage](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.md)|A simple implementation of VariableStorageBehaviour.|
|[LabelAttribute](/docs/api/csharp/yarn.unity.labelattribute.md)||
|[LanguageAttribute](/docs/api/csharp/yarn.unity.languageattribute.md)||
|[LineMetadata](/docs/api/csharp/yarn.unity.linemetadata.md)||
|[LineProviderBehaviour](/docs/api/csharp/yarn.unity.lineproviderbehaviour.md)|A  <code>UnityEngine.MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.|
|[LineView](/docs/api/csharp/yarn.unity.lineview.md)|A Dialogue View that presents lines of dialogue, using Unity UI elements.|
|[Localization](/docs/api/csharp/yarn.unity.localization.md)||
|[LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md)|Represents a line, ready to be presented to the user in the localisation they have specified.|
|[MarkupPalette](/docs/api/csharp/yarn.unity.markuppalette.md)|Represents a collection of marker names and colours.|
|[OptionsListView](/docs/api/csharp/yarn.unity.optionslistview.md)||
|[OptionView](/docs/api/csharp/yarn.unity.optionview.md)||
|[SampleRenderDetector](/docs/api/csharp/yarn.unity.samplerenderdetector.md)|Detects if the render pipeline is different from the one the samples were created with, and warn you that things might look odd.|
|[SerializedDictionary](/docs/api/csharp/yarn.unity.serializeddictionary.md)|An  <code>System.Collections.Generic.IDictionary`2</code>  that can be serialized as part of a Unity object.|
|[ShowIfAttribute](/docs/api/csharp/yarn.unity.showifattribute.md)||
|[UnityEventString](/docs/api/csharp/yarn.unity.unityeventstring.md)||
|[VariableStorageBehaviour](/docs/api/csharp/yarn.unity.variablestoragebehaviour.md)|A  <code>UnityEngine.MonoBehaviour</code>  that a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  uses to store and retrieve variables.|
|[VisibilityAttribute](/docs/api/csharp/yarn.unity.visibilityattribute.md)||
|[VoiceOverView](/docs/api/csharp/yarn.unity.voiceoverview.md)|A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that plays voice-over  <code>UnityEngine.AudioClip</code> s for lines of dialogue.|
|[YarnAsync](/docs/api/csharp/yarn.unity.yarnasync.md)||
|[YarnCommandAttribute](/docs/api/csharp/yarn.unity.yarncommandattribute.md)|An attribute that marks a method on an object as a command.|
|[YarnFunctionAttribute](/docs/api/csharp/yarn.unity.yarnfunctionattribute.md)|Marks the method as a function to be registered with the running instance's library.|
|[YarnNodeAttribute](/docs/api/csharp/yarn.unity.yarnnodeattribute.md)|Specifies that a field represents a reference to a named Yarn node that exists in a Yarn project.|
|[YarnProject](/docs/api/csharp/yarn.unity.yarnproject.md)||

## Enums

|Name|Description|
|:---|:---|
|[LocalizationType](/docs/api/csharp/yarn.unity.localizationtype.md)||
|[RegistrationType](/docs/api/csharp/yarn.unity.registrationtype.md)||

## Interfaces

|Name|Description|
|:---|:---|
|[IActionRegistration](/docs/api/csharp/yarn.unity.iactionregistration.md)||
|[ICommand](/docs/api/csharp/yarn.unity.icommand.md)||
|[IGeneratedVariableStorage](/docs/api/csharp/yarn.unity.igeneratedvariablestorage.md)|An interface that works with  <a href="yarn.unity.generatedvariablestorageextensions.md">GeneratedVariableStorageExtensions</a>  to add helper methods used by generated variable storage classes.|

## Namespaces

|Name|Description|
|:---|:---|
|[Yarn.Unity.UnityLocalization](/docs/api/csharp/yarn.unity.unitylocalization.md)||

## Structs

|Name|Description|
|:---|:---|
|[Culture](/docs/api/csharp/yarn.unity.culture.md)|Holds information about a language.|
|[LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)||
|[StringTableEntry](/docs/api/csharp/yarn.unity.stringtableentry.md)||

