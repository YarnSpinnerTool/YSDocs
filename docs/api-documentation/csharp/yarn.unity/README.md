# Yarn.Unity Namespace

## Summary

Contains classes for working with Yarn Spinner in the Unity game engine.

## Attributes

| Name                                                                 | Description                                                           |
| -------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [YarnActionAttribute](yarn.unity.yarnactionattribute/)               |                                                                       |
| [YarnParameterAttribute](yarn.unity.yarnparameterattribute/)         | Yarn parameter.                                                       |
| [YarnStateInjectorAttribute](yarn.unity.yarnstateinjectorattribute/) | Inject state for any commands in this class using this static method. |

## Classes

| Name                                                               | Description                                                                                                                                                 |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Actions](yarn.unity.actions/)                                     |                                                                                                                                                             |
| [AudioLineProvider](yarn.unity.audiolineprovider/)                 |                                                                                                                                                             |
| [CharacterColorView](yarn.unity.charactercolorview/)               |                                                                                                                                                             |
| [Cultures](yarn.unity.cultures/)                                   | Provides access to all [Culture](yarn.unity.culture/) s supported by Yarn Spinner.                                                                          |
| [DialogueAdvanceInput](yarn.unity.dialogueadvanceinput/)           | A component that listens for user input, and uses it to notify a dialogue view that the user wishes to advance to the next step in the dialogue.            |
| [DialogueCharacterNameView](yarn.unity.dialoguecharacternameview/) | A subclass of [DialogueViewBase](yarn.unity.dialogueviewbase/) that displays character names.                                                               |
| [DialogueOption](yarn.unity.dialogueoption/)                       |                                                                                                                                                             |
| [DialogueReference](yarn.unity.dialoguereference/)                 | Stores a reference to a dialogue node in a Yarn Project.                                                                                                    |
| [DialogueRunner](yarn.unity.dialoguerunner/)                       | The DialogueRunner component acts as the interface between your game and Yarn Spinner.                                                                      |
| [DialogueViewBase](yarn.unity.dialogueviewbase/)                   | A `UnityEngine.MonoBehaviour` that can present lines and options to the user, when it receives them from a [DialogueRunner](yarn.unity.dialoguerunner/) .   |
| [Effects](yarn.unity.effects/)                                     | Contains coroutine methods that apply visual effects. This class is used by [LineView](yarn.unity.lineview/) to handle animating the presentation of lines. |
| [InMemoryVariableStorage](yarn.unity.inmemoryvariablestorage/)     | A simple implementation of VariableStorageBehaviour.                                                                                                        |
| [LanguageAttribute](yarn.unity.languageattribute.md)               |                                                                                                                                                             |
| [LineMetadata](yarn.unity.linemetadata/)                           |                                                                                                                                                             |
| [LineProviderBehaviour](yarn.unity.lineproviderbehaviour/)         | A `UnityEngine.MonoBehaviour` that produces [LocalizedLine](yarn.unity.localizedline/) s, for use in Dialogue Views.                                        |
| [LineView](yarn.unity.lineview/)                                   | A Dialogue View that presents lines of dialogue, using Unity UI elements.                                                                                   |
| [Localization](yarn.unity.localization/)                           |                                                                                                                                                             |
| [LocalizedLine](yarn.unity.localizedline/)                         | Represents a line, ready to be presented to the user in the localisation they have specified.                                                               |
| [MarkupPalette](yarn.unity.markuppalette/)                         | Represents a collection of marker names and colours.                                                                                                        |
| [OptionsListView](yarn.unity.optionslistview/)                     |                                                                                                                                                             |
| [OptionView](yarn.unity.optionview/)                               |                                                                                                                                                             |
| [SampleRenderDetector](yarn.unity.samplerenderdetector.md)         | Detects if the render pipeline is different from the one the samples were created with, and warn you that things might look odd.                            |
| [SerializedDictionary](yarn.unity.serializeddictionary/)           | An ``System.Collections.Generic.IDictionary`2`` that can be serialized as part of a Unity object.                                                           |
| [TextLineProvider](yarn.unity.textlineprovider/)                   |                                                                                                                                                             |
| [VariableStorageBehaviour](yarn.unity.variablestoragebehaviour/)   | A `UnityEngine.MonoBehaviour` that a [DialogueRunner](yarn.unity.dialoguerunner/) uses to store and retrieve variables.                                     |
| [VoiceOverView](yarn.unity.voiceoverview/)                         | A subclass of [DialogueViewBase](yarn.unity.dialogueviewbase/) that plays voice-over `UnityEngine.AudioClip` s for lines of dialogue.                       |
| [YarnCommandAttribute](yarn.unity.yarncommandattribute/)           | An attribute that marks a method on an object as a command.                                                                                                 |
| [YarnFunctionAttribute](yarn.unity.yarnfunctionattribute.md)       | Marks the method as a function to be registered with the running instance's library.                                                                        |
| [YarnNodeAttribute](yarn.unity.yarnnodeattribute/)                 | Specifies that a field represents a reference to a named Yarn node that exists in a Yarn project.                                                           |
| [YarnProject](yarn.unity.yarnproject/)                             |                                                                                                                                                             |

## Enums

| Name                                             | Description |
| ------------------------------------------------ | ----------- |
| [LocalizationType](yarn.unity.localizationtype/) |             |

## Interfaces

| Name                                                   | Description |
| ------------------------------------------------------ | ----------- |
| [IActionRegistration](yarn.unity.iactionregistration/) |             |
| [ICommand](yarn.unity.icommand/)                       |             |

## Namespaces

| Name                                                             | Description |
| ---------------------------------------------------------------- | ----------- |
| [Yarn.Unity.UnityLocalization](../yarn.unity.unitylocalization/) |             |

## Structs

| Name                                             | Description                         |
| ------------------------------------------------ | ----------------------------------- |
| [Culture](yarn.unity.culture/)                   | Holds information about a language. |
| [StringTableEntry](yarn.unity.stringtableentry/) |                                     |
