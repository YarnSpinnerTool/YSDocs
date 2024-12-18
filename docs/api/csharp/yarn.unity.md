# Yarn.Unity Namespace

## Summary

Contains classes for working with Yarn Spinner in the Unity game engine.


## Attributes

|Name|Description|
|:---|:---|
|[YarnActionAttribute](/docs/api/csharp/yarn.unity.yarnactionattribute.md)||
|[YarnEditorAttribute](/docs/api/csharp/yarn.unity.yarneditorattribute.md)|The abstract base class for all Yarn Editor attributes.|

## Classes

|Name|Description|
|:---|:---|
|[ActionRegistrationExtension](/docs/api/csharp/yarn.unity.actionregistrationextension.md)|Contains extension methods for  <a href="yarn.unity.iactionregistration.md">IActionRegistration</a>  objects.|
|[Actions](/docs/api/csharp/yarn.unity.actions.md)||
|[AsyncDialogueViewBase](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.md)|A  <code>UnityEngine.MonoBehaviour</code>  that can present lines and options to the user, when it receives them from a   <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .|
|[AsyncLineView](/docs/api/csharp/yarn.unity.asynclineview.md)|A Dialogue View that presents lines of dialogue, using Unity UI elements.|
|[AsyncOptionItem](/docs/api/csharp/yarn.unity.asyncoptionitem.md)||
|[AsyncOptionsView](/docs/api/csharp/yarn.unity.asyncoptionsview.md)|Receives options from a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> , and displays and manages a collection of  <a href="yarn.unity.asyncoptionitem.md">AsyncOptionItem</a>  views for the user to choose from.|
|[AttributeMarkerProcessor](/docs/api/csharp/yarn.unity.attributemarkerprocessor.md)|An attribute marker processor receives a marker found in a Yarn line, and optionally rewrites the marker and its children into a new form.|
|[BuiltinLocalisedLineProvider](/docs/api/csharp/yarn.unity.builtinlocalisedlineprovider.md)||
|[CharacterColorView](/docs/api/csharp/yarn.unity.charactercolorview.md)|A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that updates the colour of a  <code>TMPro.TMP_Text</code>  object based on the character speaking a line. names.|
|[Cultures](/docs/api/csharp/yarn.unity.cultures.md)|Provides access to all  <a href="yarn.unity.culture.md">Culture</a> s supported by Yarn Spinner.|
|[DialogueAdvanceInput](/docs/api/csharp/yarn.unity.dialogueadvanceinput.md)|A component that listens for user input, and uses it to notify a dialogue view that the user wishes to advance to the next step in the dialogue.|
|[DialogueCharacterNameView](/docs/api/csharp/yarn.unity.dialoguecharacternameview.md)|A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that displays character names.|
|[DialogueOption](/docs/api/csharp/yarn.unity.dialogueoption.md)||
|[DialogueReference](/docs/api/csharp/yarn.unity.dialoguereference.md)|Stores a reference to a dialogue node in a Yarn Project.|
|[DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)||
|[DialogueViewBase](/docs/api/csharp/yarn.unity.dialogueviewbase.md)|Implements the Yarn Spinner 2 callback-based API for dialogue views using Yarn Spinner 3.|
|[Effects](/docs/api/csharp/yarn.unity.effects.md)|Contains coroutine methods that apply visual effects. This class is used by  <a href="yarn.unity.lineview.md">LineView</a>  to handle animating the presentation of lines.|
|[GeneratedVariableStorageExtensions](/docs/api/csharp/yarn.unity.generatedvariablestorageextensions.md)||
|[GroupAttribute](/docs/api/csharp/yarn.unity.groupattribute.md)|Shows a header above this property and the following properties that have the same group name, optionally as a foldout.|
|[HideIfAttribute](/docs/api/csharp/yarn.unity.hideifattribute.md)|Hides this property when a condition is true.|
|[IndentAttribute](/docs/api/csharp/yarn.unity.indentattribute.md)|Indents a property in the Unity Inspector.|
|[InMemoryVariableStorage](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.md)|A simple implementation of VariableStorageBehaviour.|
|[LabelAttribute](/docs/api/csharp/yarn.unity.labelattribute.md)|Overrides the displayed label of the property in the Unity Inspector.|
|[LanguageAttribute](/docs/api/csharp/yarn.unity.languageattribute.md)||
|[LineAdvancer](/docs/api/csharp/yarn.unity.lineadvancer.md)|A dialogue view that listens for user input and sends requests to a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to advance the presentation of the current line, either by asking a dialogue runner to hurry up its delivery, advance to the next line, or cancel the entire dialogue session.|
|[LineMetadata](/docs/api/csharp/yarn.unity.linemetadata.md)||
|[LineProviderBehaviour](/docs/api/csharp/yarn.unity.lineproviderbehaviour.md)|A  <code>UnityEngine.MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.|
|[LineView](/docs/api/csharp/yarn.unity.lineview.md)|A Dialogue View that presents lines of dialogue, using Unity UI elements.|
|[Localization](/docs/api/csharp/yarn.unity.localization.md)||
|[LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md)|Represents a line, ready to be presented to the user in the localisation they have specified.|
|[MarkupPalette](/docs/api/csharp/yarn.unity.markuppalette.md)|Represents a collection of marker names and colours.|
|[MessageBoxAttribute](/docs/api/csharp/yarn.unity.messageboxattribute.md)|Shows a message box on the property.|
|[MustNotBeNullAttribute](/docs/api/csharp/yarn.unity.mustnotbenullattribute.md)|Shows an error message box if this property is null.|
|[MustNotBeNullWhenAttribute](/docs/api/csharp/yarn.unity.mustnotbenullwhenattribute.md)|Shows an error message box if this property is null and the variable indicated by  <a href="yarn.unity.mustnotbenullwhenattribute.condition.md">Condition</a>  is false.|
|[OptionsListView](/docs/api/csharp/yarn.unity.optionslistview.md)||
|[OptionView](/docs/api/csharp/yarn.unity.optionview.md)||
|[SampleRenderDetector](/docs/api/csharp/yarn.unity.samplerenderdetector.md)|Detects if the render pipeline is different from the one the samples were created with, and warn you that things might look odd.|
|[SerializableDictionary](/docs/api/csharp/yarn.unity.serializabledictionary-1.md)||
|[SerializableDictionary](/docs/api/csharp/yarn.unity.serializabledictionary-2.md)||
|[SerializableDictionary](/docs/api/csharp/yarn.unity.serializabledictionary-3.md)||
|[SerializableDictionaryBase](/docs/api/csharp/yarn.unity.serializabledictionarybase-1.md)||
|[SerializableDictionaryBase](/docs/api/csharp/yarn.unity.serializabledictionarybase-2.md)||
|[ShowIfAttribute](/docs/api/csharp/yarn.unity.showifattribute.md)|Shows this property only when a condition is true.|
|[StyleMarkerProcessor](/docs/api/csharp/yarn.unity.stylemarkerprocessor.md)|An attribute marker processor that inserts TextMeshPro style tags where Yarn Spinner  <code>[style]</code>  tags appear in a line.|
|[TemporalMarkupHandler](/docs/api/csharp/yarn.unity.temporalmarkuphandler.md)|A  <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a>  is an object that reacts to the delivery of a line of dialogue, and can optionally control the timing of that delivery.|
|[TypewriterHandler](/docs/api/csharp/yarn.unity.typewriterhandler.md)|A  <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a>  that progressively reveals the text of a line at a fixed rate of time.|
|[UnityEventString](/docs/api/csharp/yarn.unity.unityeventstring.md)|A  <code>UnityEngine.Events.UnityEvent</code>  that takes a single  <code>string</code>  parameter.|
|[VariableStorageBehaviour](/docs/api/csharp/yarn.unity.variablestoragebehaviour.md)|A  <code>UnityEngine.MonoBehaviour</code>  that a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  uses to store and retrieve variables.|
|[VisibilityAttribute](/docs/api/csharp/yarn.unity.visibilityattribute.md)|Controls whether a property is visible or not in the Unity Inspector.|
|[VoiceOverView](/docs/api/csharp/yarn.unity.voiceoverview.md)|A subclass of  <a href="yarn.unity.asyncdialogueviewbase.md">AsyncDialogueViewBase</a>  that plays voice-over <code>UnityEngine.AudioClip</code> s for lines of dialogue.|
|[YarnCommandAttribute](/docs/api/csharp/yarn.unity.yarncommandattribute.md)|An attribute that marks a method on an object as a command.|
|[YarnFunctionAttribute](/docs/api/csharp/yarn.unity.yarnfunctionattribute.md)|Marks the method as a function to be registered with the running instance's library.|
|[YarnNodeAttribute](/docs/api/csharp/yarn.unity.yarnnodeattribute.md)|Specifies that a field represents a reference to a named Yarn node that exists in a Yarn project.|
|[YarnProject](/docs/api/csharp/yarn.unity.yarnproject.md)||
|[YarnTaskCompletionSource](/docs/api/csharp/yarn.unity.yarntaskcompletionsource-1.md)||
|[YarnTaskCompletionSource](/docs/api/csharp/yarn.unity.yarntaskcompletionsource-2.md)||
|[YarnTaskExtensions](/docs/api/csharp/yarn.unity.yarntaskextensions.md)||

## Enums

|Name|Description|
|:---|:---|
|[LocalizationType](/docs/api/csharp/yarn.unity.localizationtype.md)||
|[RegistrationType](/docs/api/csharp/yarn.unity.registrationtype.md)||

## Interfaces

|Name|Description|
|:---|:---|
|[IActionRegistration](/docs/api/csharp/yarn.unity.iactionregistration.md)|Contains methods that allow adding and removing Yarn commands and functions.|
|[ICommand](/docs/api/csharp/yarn.unity.icommand.md)||
|[IGeneratedVariableStorage](/docs/api/csharp/yarn.unity.igeneratedvariablestorage.md)|An interface that works with  <a href="yarn.unity.generatedvariablestorageextensions.md">GeneratedVariableStorageExtensions</a>  to add helper methods used by generated variable storage classes.|
|[IYarnTask](/docs/api/csharp/yarn.unity.iyarntask.md)||

## Namespaces

|Name|Description|
|:---|:---|
|[Yarn.Unity.UnityLocalization](/docs/api/csharp/yarn.unity.unitylocalization.md)||

## Structs

|Name|Description|
|:---|:---|
|[Culture](/docs/api/csharp/yarn.unity.culture.md)|Holds information about a language.|
|[LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)|A Line Cancellation Token stores information about whether a dialogue view should stop its delivery.|
|[StringTableEntry](/docs/api/csharp/yarn.unity.stringtableentry.md)||
|[YarnTask](/docs/api/csharp/yarn.unity.yarntask-1.md)||
|[YarnTask](/docs/api/csharp/yarn.unity.yarntask-2.md)||
|[YarnTaskMethodBuilder](/docs/api/csharp/yarn.unity.yarntaskmethodbuilder-1.md)||
|[YarnTaskMethodBuilder](/docs/api/csharp/yarn.unity.yarntaskmethodbuilder-2.md)||

