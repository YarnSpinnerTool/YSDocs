# Project

Class in [Yarn.Compiler](yarn.compiler.md)

Inherits from `System.Object`

## Summary

Yarn Projects represent instructions on where to find Yarn scripts and associated assets, and how they should be compiled.

```csharp
public class Project
```

## Classes

| Name                                                          | Description                                                                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| [LocalizationInfo](yarn.compiler.project.localizationinfo.md) | Stores the locations of where localized assets and a localized string table for a Yarn Project may be found. |

## Constructors

| Name                                                        | Description                                                                  |
| ----------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [Project()](yarn.compiler.project..ctor-1.md)               | Initializes a new instance of the [Project](yarn.compiler.project.md) class. |
| [Project(string,string?)](yarn.compiler.project..ctor-2.md) | Initializes a new instance of the [Project](yarn.compiler.project.md) class. |

## Fields

| Name                                                                              | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| [CurrentProjectFileVersion](yarn.compiler.project.currentprojectfileversion.md)   | The current version of `.yarnproject` file format.                                |
| [WorkspaceRootPlaceholder](yarn.compiler.project.workspacerootplaceholder.md)     | A placeholder string that represents the location of the workspace root in paths. |
| [YarnSpinnerProjectVersion2](yarn.compiler.project.yarnspinnerprojectversion2.md) | A version number representing Yarn Spinner 2.                                     |
| [YarnSpinnerProjectVersion3](yarn.compiler.project.yarnspinnerprojectversion3.md) | A version number representing Yarn Spinner 3.                                     |

## Methods

| Name                                                                       | Description                                                                                             |
| -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [GetJson()](yarn.compiler.project.getjson.md)                              | Gets a string containing JSON-formatted text that represents this [Project](yarn.compiler.project.md) . |
| [IsMatchingPath(string)](yarn.compiler.project.ismatchingpath.md)          | Gets a value indicating whether `path` is a path that is included in this project.                      |
| [IsValidVersionNumber(int)](yarn.compiler.project.isvalidversionnumber.md) | Gets a value indicating whether `number` is a valid Yarn Spinner version number.                        |
| [LoadFromFile(string,string?)](yarn.compiler.project.loadfromfile.md)      | Loads and parses a [Project](yarn.compiler.project.md) from a file on disk.                             |
| [SaveToFile(string)](yarn.compiler.project.savetofile.md)                  | Saves a [Project](yarn.compiler.project.md) as JSON-formatted text to a file on disk.                   |

## Properties

| Name                                                                                  | Description                                                                                                                                                                       |
| ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AllowLanguagePreviewFeatures](yarn.compiler.project.allowlanguagepreviewfeatures.md) | Gets or sets a value indicating whether compiler features that are not intended for production use are allowed.                                                                   |
| [BaseLanguage](yarn.compiler.project.baselanguage.md)                                 | Gets or sets the base language of the project, as an IETF BCP-47 language tag.                                                                                                    |
| [CompilerOptions](yarn.compiler.project.compileroptions.md)                           | Gets or sets a dictionary containing instructions that control how the Yarn Spinner compiler should compile a project.                                                            |
| [Definitions](yarn.compiler.project.definitions.md)                                   | Gets or sets the path to a JSON file containing command and function definitions that this project references.                                                                    |
| [DefinitionsFiles](yarn.compiler.project.definitionsfiles.md)                         | Gets the absolute paths to the project's Definitions files.                                                                                                                       |
| [DefinitionsPath](yarn.compiler.project.definitionspath.md)                           | Gets the path to the Definitions file, relative to this project's location.                                                                                                       |
| [ExcludeFilePatterns](yarn.compiler.project.excludefilepatterns.md)                   | Gets or sets the collection of file search patterns that should be excluded from this project.                                                                                    |
| [ExtensionData](yarn.compiler.project.extensiondata.md)                               | Contains any data parsed from the source file that was not matched to a property on this type.                                                                                    |
| [FileVersion](yarn.compiler.project.fileversion.md)                                   | Gets or sets the file version of the project.                                                                                                                                     |
| [Localisation](yarn.compiler.project.localisation.md)                                 | Gets or sets the collection of [LocalizationInfo](yarn.compiler.project.localizationinfo.md) objects that store information about where localized data for this project is found. |
| [Path](yarn.compiler.project.path.md)                                                 | Gets the path that the [Project](yarn.compiler.project.md) was loaded from.                                                                                                       |
| [SourceFilePatterns](yarn.compiler.project.sourcefilepatterns.md)                     | Gets or sets the collection of file search patterns used to locate Yarn files that form this project.                                                                             |
| [SourceFiles](yarn.compiler.project.sourcefiles.md)                                   | Gets the collection of Yarn files that should be used to compile the project.                                                                                                     |
| [WorkspaceRootPath](yarn.compiler.project.workspacerootpath.md)                       | The location of the root of the workspace in which this project is located.                                                                                                       |
