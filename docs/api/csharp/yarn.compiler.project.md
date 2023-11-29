# Project

Class in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Yarn Projects represent instructions on where to find Yarn scripts and
associated assets, and how they should be compiled.


```csharp
public class Project
```

## Classes

|Name|Description|
|:---|:---|
|[LocalizationInfo](/api/csharp/yarn.compiler.project.localizationinfo.md)|Stores the locations of where localized assets and a localized string table for a Yarn Project may be found.|

## Fields

|Name|Description|
|:---|:---|
|[CurrentProjectFileVersion](/api/csharp/yarn.compiler.project.currentprojectfileversion.md)|The current version of  <code>.yarnproject</code>  file format.|

## Methods

|Name|Description|
|:---|:---|
|[GetJson()](/api/csharp/yarn.compiler.project.getjson.md)|Gets a string containing JSON-formatted text that represents this <a href="yarn.compiler.project.md">Project</a> .|
|[IsMatchingPath(string)](/api/csharp/yarn.compiler.project.ismatchingpath.md)|Gets a value indicating whether  <code>path</code>  is a path that is included in this project.|
|[LoadFromFile(string)](/api/csharp/yarn.compiler.project.loadfromfile.md)|Loads and parses a  <a href="yarn.compiler.project.md">Project</a>  from a file on disk.|
|[SaveToFile(string)](/api/csharp/yarn.compiler.project.savetofile.md)|Saves a  <a href="yarn.compiler.project.md">Project</a>  as JSON-formatted text to a file on disk.|

## Properties

|Name|Description|
|:---|:---|
|[BaseLanguage](/api/csharp/yarn.compiler.project.baselanguage.md)|Gets or sets the base language of the project, as an IETF BCP-47 language tag.|
|[CompilerOptions](/api/csharp/yarn.compiler.project.compileroptions.md)|Gets or sets a dictionary containing instructions that control how the Yarn Spinner compiler should compile a project.|
|[Definitions](/api/csharp/yarn.compiler.project.definitions.md)|Gets or sets the path to a JSON file containing command and function definitions that this project references.|
|[DefinitionsPath](/api/csharp/yarn.compiler.project.definitionspath.md)|Gets the path to the Definitions file, relative to this project's location.|
|[ExcludeFilePatterns](/api/csharp/yarn.compiler.project.excludefilepatterns.md)|Gets or sets the collection of file search patterns that should be excluded from this project.|
|[FileVersion](/api/csharp/yarn.compiler.project.fileversion.md)|Gets or sets the file version of the project.|
|[Localisation](/api/csharp/yarn.compiler.project.localisation.md)|Gets or sets the collection of  <a href="yarn.compiler.project.localizationinfo.md">LocalizationInfo</a>  objects that store information about where localized data for this project is found.|
|[Path](/api/csharp/yarn.compiler.project.path.md)|Gets the path that the  <a href="yarn.compiler.project.md">Project</a>  was loaded from.|
|[SourceFilePatterns](/api/csharp/yarn.compiler.project.sourcefilepatterns.md)|Gets or sets the collection of file search patterns used to locate Yarn files that form this project.|
|[SourceFiles](/api/csharp/yarn.compiler.project.sourcefiles.md)|Gets the collection of Yarn files that should be used to compile the project.|

