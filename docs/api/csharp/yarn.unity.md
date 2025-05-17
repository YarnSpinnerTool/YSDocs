# Yarn.Unity Namespace

## Summary

Contains classes for working with Yarn Spinner in the Unity game engine.


## Attributes

|Name|Description|
|:---|:---|
|[YarnActionAttribute](/docs/api/csharp/yarn.unity.yarnactionattribute.md)||

## Classes

|Name|Description|
|:---|:---|
|[ActionMarkupHandler](/docs/api/csharp/yarn.unity.actionmarkuphandler.md)|This is an abstract monobehaviour that conforms to the  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a>  interface.|
|[ActionRegistrationExtension](/docs/api/csharp/yarn.unity.actionregistrationextension.md)|Contains extension methods for  <a href="yarn.unity.iactionregistration.md">IActionRegistration</a>  objects.|
|[Actions](/docs/api/csharp/yarn.unity.actions.md)||
|[BuiltinLocalisedLineProvider](/docs/api/csharp/yarn.unity.builtinlocalisedlineprovider.md)||
|[Cultures](/docs/api/csharp/yarn.unity.cultures.md)|Provides access to all  <a href="yarn.unity.culture.md">Culture</a> s supported by Yarn Spinner.|
|[DialogueOption](/docs/api/csharp/yarn.unity.dialogueoption.md)||
|[DialoguePresenterBase](/docs/api/csharp/yarn.unity.dialoguepresenterbase.md)|A  <code>UnityEngine.MonoBehaviour</code>  that can present lines and options to the user, when it receives them from a   <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> .|
|[DialogueReference](/docs/api/csharp/yarn.unity.dialoguereference.md)|Stores a reference to a dialogue node in a Yarn Project.|
|[DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)||
|[Effects](/docs/api/csharp/yarn.unity.effects.md)|Contains coroutine methods that apply visual effects. This class is used by  <code>LineView</code>  to handle animating the presentation of lines.|
|[GeneratedVariableStorageExtensions](/docs/api/csharp/yarn.unity.generatedvariablestorageextensions.md)||
|[InMemoryVariableStorage](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.md)|A simple implementation of VariableStorageBehaviour.|
|[LineAdvancer](/docs/api/csharp/yarn.unity.lineadvancer.md)|A dialogue presenter that listens for user input and sends requests to a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to advance the presentation of the current line, either by asking a dialogue runner to hurry up its delivery, advance to the next line, or cancel the entire dialogue session.|
|[LineMetadata](/docs/api/csharp/yarn.unity.linemetadata.md)||
|[LinePresenter](/docs/api/csharp/yarn.unity.linepresenter.md)|A Dialogue View that presents lines of dialogue, using Unity UI elements.|
|[LinePresenterButtonHandler](/docs/api/csharp/yarn.unity.linepresenterbuttonhandler.md)||
|[LineProviderBehaviour](/docs/api/csharp/yarn.unity.lineproviderbehaviour.md)|A  <code>UnityEngine.MonoBehaviour</code>  that produces  <a href="yarn.unity.localizedline.md">LocalizedLine</a> s, for use in Dialogue Views.|
|[Localization](/docs/api/csharp/yarn.unity.localization.md)||
|[LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md)|Represents a line, ready to be presented to the user in the localisation they have specified.|
|[MarkupPalette](/docs/api/csharp/yarn.unity.markuppalette.md)|Represents a collection of marker names and colours.|
|[OptionItem](/docs/api/csharp/yarn.unity.optionitem.md)||
|[OptionsPresenter](/docs/api/csharp/yarn.unity.optionspresenter.md)|Receives options from a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> , and displays and manages a collection of  <a href="yarn.unity.optionitem.md">OptionItem</a>  views for the user to choose from.|
|[PauseEventProcessor](/docs/api/csharp/yarn.unity.pauseeventprocessor.md)|Allows pausing the current typewrite through [pause/] markers.|
|[ReplacementMarkupHandler](/docs/api/csharp/yarn.unity.replacementmarkuphandler.md)|An attribute marker processor receives a marker found in a Yarn line, and optionally rewrites the marker and its children into a new form.|
|[SerializableDictionary](/docs/api/csharp/yarn.unity.serializabledictionary-1.md)||
|[SerializableDictionary](/docs/api/csharp/yarn.unity.serializabledictionary-2.md)||
|[SerializableDictionary](/docs/api/csharp/yarn.unity.serializabledictionary-3.md)||
|[SerializableDictionaryBase](/docs/api/csharp/yarn.unity.serializabledictionarybase-1.md)||
|[SerializableDictionaryBase](/docs/api/csharp/yarn.unity.serializabledictionarybase-2.md)||
|[StyleMarkerProcessor](/docs/api/csharp/yarn.unity.stylemarkerprocessor.md)|An attribute marker processor that inserts TextMeshPro style tags where Yarn Spinner  <code>[style]</code>  tags appear in a line.|
|[UnityEventString](/docs/api/csharp/yarn.unity.unityeventstring.md)|A  <code>UnityEngine.Events.UnityEvent</code>  that takes a single  <code>string</code>  parameter.|
|[VariableStorageBehaviour](/docs/api/csharp/yarn.unity.variablestoragebehaviour.md)|A  <code>UnityEngine.MonoBehaviour</code>  that a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  uses to store and retrieve variables.|
|[VoiceOverPresenter](/docs/api/csharp/yarn.unity.voiceoverpresenter.md)|A subclass of  <a href="yarn.unity.dialoguepresenterbase.md">DialoguePresenterBase</a>  that plays voice-over <code>UnityEngine.AudioClip</code> s for lines of dialogue.|
|[YarnCommandAttribute](/docs/api/csharp/yarn.unity.yarncommandattribute.md)|An attribute that marks a method on an object as a command.|
|[YarnFunctionAttribute](/docs/api/csharp/yarn.unity.yarnfunctionattribute.md)|Marks the method as a function to be registered with the running instance's library.|
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
|[IActionMarkupHandler](/docs/api/csharp/yarn.unity.iactionmarkuphandler.md)|A  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a>  is an object that reacts to the delivery of a line of dialogue, and can optionally control the timing of that delivery.|
|[IActionRegistration](/docs/api/csharp/yarn.unity.iactionregistration.md)|Contains methods that allow adding and removing Yarn commands and functions.|
|[IAssetProvider](/docs/api/csharp/yarn.unity.iassetprovider.md)|Contains methods for accessing assets of a given type stored within an object.|
|[ICommand](/docs/api/csharp/yarn.unity.icommand.md)||
|[IGeneratedVariableStorage](/docs/api/csharp/yarn.unity.igeneratedvariablestorage.md)|An interface that works with  <a href="yarn.unity.generatedvariablestorageextensions.md">GeneratedVariableStorageExtensions</a>  to add helper methods used by generated variable storage classes.|
|[ILineProvider](/docs/api/csharp/yarn.unity.ilineprovider.md)|Contains methods for retrieving user-facing localized content, given non-localized line IDs.|
|[IYarnTask](/docs/api/csharp/yarn.unity.iyarntask.md)||

## Namespaces

|Name|Description|
|:---|:---|
|[Yarn.Unity.Legacy](/docs/api/csharp/yarn.unity.legacy.md)|Contains compatibility features for code designed to work with earlier versions of Yarn Spinner for Unity.|
|[Yarn.Unity.Samples](/docs/api/csharp/yarn.unity.samples.md)||
|[Yarn.Unity.UnityLocalization](/docs/api/csharp/yarn.unity.unitylocalization.md)|Contains classes for working with the Unity Localization system and Yarn Spinner.|

## Structs

|Name|Description|
|:---|:---|
|[Culture](/docs/api/csharp/yarn.unity.culture.md)|Holds information about a language.|
|[LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)|A Line Cancellation Token stores information about whether a dialogue view should stop its delivery.|
|[StringTableEntry](/docs/api/csharp/yarn.unity.stringtableentry.md)||
|[YarnTask](/docs/api/csharp/yarn.unity.yarntask-1.md)||
|[YarnTask](/docs/api/csharp/yarn.unity.yarntask-2.md)||

