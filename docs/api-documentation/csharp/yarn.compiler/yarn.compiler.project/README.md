# Project

Class in [Yarn.Compiler](../)

Inherits from `System.Object`

## Summary

Yarn Projects represent instructions on where to find Yarn scripts and associated assets, and how they should be compiled.

```csharp
public class Project
```

## Classes

| Name                                                        | Description                                                                                                  |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| [LocalizationInfo](yarn.compiler.project.localizationinfo/) | Stores the locations of where localized assets and a localized string table for a Yarn Project may be found. |

## Fields

| Name                                                                            | Description                                        |
| ------------------------------------------------------------------------------- | -------------------------------------------------- |
| [CurrentProjectFileVersion](yarn.compiler.project.currentprojectfileversion.md) | The current version of `.yarnproject` file format. |

## Methods

| Name                                                              | Description                                                                        |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [GetJson()](yarn.compiler.project.getjson.md)                     | Gets a string containing JSON-formatted text that represents this [Project](./) .  |
| [IsMatchingPath(string)](yarn.compiler.project.ismatchingpath.md) | Gets a value indicating whether `path` is a path that is included in this project. |
| [LoadFromFile(string)](yarn.compiler.project.loadfromfile.md)     | Loads and parses a [Project](./) from a file on disk.                              |
| [SaveToFile(string)](yarn.compiler.project.savetofile.md)         | Saves a [Project](./) as JSON-formatted text to a file on disk.                    |

## Properties

| Name                                                                | Description                                                                                                                                                                     |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [BaseLanguage](yarn.compiler.project.baselanguage.md)               | Gets or sets the base language of the project, as an IETF BCP-47 language tag.                                                                                                  |
| [CompilerOptions](yarn.compiler.project.compileroptions.md)         | Gets or sets a dictionary containing instructions that control how the Yarn Spinner compiler should compile a project.                                                          |
| [Definitions](yarn.compiler.project.definitions.md)                 | Gets or sets the path to a JSON file containing command and function definitions that this project references.                                                                  |
| [DefinitionsPath](yarn.compiler.project.definitionspath.md)         | Gets the path to the Definitions file, relative to this project's location.                                                                                                     |
| [ExcludeFilePatterns](yarn.compiler.project.excludefilepatterns.md) | Gets or sets the collection of file search patterns that should be excluded from this project.                                                                                  |
| [FileVersion](yarn.compiler.project.fileversion.md)                 | Gets or sets the file version of the project.                                                                                                                                   |
| [Localisation](yarn.compiler.project.localisation.md)               | Gets or sets the collection of [LocalizationInfo](yarn.compiler.project.localizationinfo/) objects that store information about where localized data for this project is found. |
| [Path](yarn.compiler.project.path.md)                               | Gets the path that the [Project](./) was loaded from.                                                                                                                           |
| [SourceFilePatterns](yarn.compiler.project.sourcefilepatterns.md)   | Gets or sets the collection of file search patterns used to locate Yarn files that form this project.                                                                           |
| [SourceFiles](yarn.compiler.project.sourcefiles.md)                 | Gets the collection of Yarn files that should be used to compile the project.                                                                                                   |
