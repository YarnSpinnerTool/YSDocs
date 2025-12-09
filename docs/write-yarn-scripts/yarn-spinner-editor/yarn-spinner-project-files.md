---
description: Learn about Yarn Spinner Project files.
icon: file
---

# Yarn Spinner Project Files

A `.yarnproject` file is a JSON file that tells Yarn Spinner which Yarn scripts to compile, how to find localised content, and other project configuration options.

Yarn Projects are used by the Yarn Spinner VS Code extension, game engines (Unity, Godot, Unreal), and the command line tools to understand how your dialogue files fit together.

### Creating a Yarn Project File

You can create a `.yarnproject` file manually, or use your game engine's tools:

* **Unity:** Open the Assets menu and choose Yarn Spinner → Yarn Project
* **Godot:** Open Project → Tools → YarnSpinner → Create Yarn Project
* **VS Code / Manual:** Create a new file with the `.yarnproject` extension and add the JSON structure below

### File Format

A `.yarnproject` file is a JSON document with the following structure:

<pre class="language-json"><code class="lang-json">{
  "projectFileVersion": 3,
<strong>  "sourceFiles": ["**/*.yarn"],
</strong>  },
}
</code></pre>

### Properties Reference

#### projectFileVersion

**Required.** An integer that identifies which version of the project file format is being used.

* Use `3` for Yarn Spinner 3.x projects
* Use `2` for Yarn Spinner 2.3+ projects

When upgrading from Yarn Spinner 2.x to 3.x, you will need to change this value from `2` to `3`.

```json
"projectFileVersion": 3
```

#### sourceFiles

**Required.** An array of file patterns that specify which Yarn scripts (`.yarn` files) should be included in this project.

Patterns use [glob syntax](https://en.wikipedia.org/wiki/Glob_\(programming\)), including support for:

* `*` matches any characters except path separators
* `**` matches any characters including path separators (globstar)
* `?` matches a single character

```json
"sourceFiles": ["**/*.yarn"]
```

**Common patterns:**

| Pattern              | Matches                                                              |
| -------------------- | -------------------------------------------------------------------- |
| `**/*.yarn`          | All `.yarn` files in the project folder and all subfolders           |
| `*.yarn`             | All `.yarn` files in the same folder as the `.yarnproject` file only |
| `Dialogue/**/*.yarn` | All `.yarn` files in the `Dialogue` folder and its subfolders        |
| `../Common.yarn`     | A specific file in the parent directory                              |

You can include multiple patterns:

```json
"sourceFiles": [
  "**/*.yarn",
  "../SharedDialogue/*.yarn"
]
```

If a file matches multiple patterns, it will only be included once.

#### excludeFiles

**Optional.** An array of file patterns that specify which Yarn scripts should be excluded from compilation, even if they match a pattern in `sourceFiles`.

This is useful for excluding backup folders, build output directories, or work in progress files.

```json
"excludeFiles": [
  "**/backup/**",
  "**/~*",
  "WIP_*.yarn"
]
```

**Common exclusion patterns:**

| Pattern              | Excludes                                                         |
| -------------------- | ---------------------------------------------------------------- |
| `**/backup/**`       | Any files inside folders named `backup`                          |
| `**/*~/**`           | Folders ending with `~` (Unity's convention for ignored folders) |
| `**/build/**`        | Build output directories                                         |
| `**/node_modules/**` | Node.js dependencies (if your project uses them)                 |
| `Test_*.yarn`        | Files starting with `Test_`                                      |

{% hint style="info" %}
By default, newly created `.yarnproject` files in Unity exclude any `.yarn` files in folders ending with `~`. This follows Unity's convention for ignoring certain folders.&#x20;
{% endhint %}

#### baseLanguage

**Optional.** An [IETF BCP 47 language tag](https://en.wikipedia.org/wiki/IETF_language_tag) indicating the language your source Yarn scripts are written in.

```json
"baseLanguage": "en"
```

**Common language tags:**

| Tag       | Language                 |
| --------- | ------------------------ |
| `en`      | English                  |
| `en-AU`   | English (Australia)      |
| `en-GB`   | English (United Kingdom) |
| `en-US`   | English (United States)  |
| `de`      | German                   |
| `fr`      | French                   |
| `ja`      | Japanese                 |
| `zh-Hans` | Chinese (Simplified)     |

If not specified, Yarn Spinner will use your computer's current locale.

#### localisation

**Optional.** A dictionary that describes where localised resources can be found for each language. Each key is a language tag, and each value is an object with the following properties:

* `strings`: Path to a file containing localised line text (typically a CSV file)
* `assets`: Path to a directory containing localised assets (such as voiceover audio)

```json
"localisation": {
  "en": {
    "assets": "./voiceover/en/"
  },
  "de": {
    "strings": "./localisation/de.csv",
    "assets": "./voiceover/de/"
  },
  "fr": {
    "strings": "./localisation/fr.csv",
    "assets": "./voiceover/fr/"
  }
}
```

Paths are relative to the location of the `.yarnproject` file.

#### definitions

**Optional.** Path to a JSON file containing command and function definitions used by the project. This file uses the `.ysls.json` extension and follows the [ysls.json schema](https://github.com/YarnSpinnerTool/YarnSpinner/blob/main/YarnSpinner.LanguageServer/src/Server/Documentation/ysls.schema.json).

```json
"definitions": "MyGameCommands.ysls.json"
```

\{% hint style="info" %\} If you're using Yarn Spinner for Unity, command and function definitions are automatically detected from your C# code. You only need a `.ysls.json` file if you're using a different game engine or want to provide additional documentation. \{% endhint %\}

#### compilerOptions

**Optional.** An object containing additional settings used by the Yarn Spinner compiler. This is reserved for future use and currently has no defined options.

```json
"compilerOptions": {}
```

### Complete Example

Here's a complete example of a `.yarnproject` file for a game with multiple languages:

```json
{
  "projectFileVersion": 3,
  "sourceFiles": [
    "Dialogue/**/*.yarn",
    "Barks/**/*.yarn"
  ],
  "excludeFiles": [
    "**/backup/**",
    "**/~*",
    "**/*.test.yarn"
  ],
  "baseLanguage": "en",
  "localisation": {
    "en": {
      "assets": "./Audio/Voiceover/en/"
    },
    "de": {
      "strings": "./Localisation/de.csv",
      "assets": "./Audio/Voiceover/de/"
    },
    "fr": {
      "strings": "./Localisation/fr.csv",
      "assets": "./Audio/Voiceover/fr/"
    },
    "ja": {
      "strings": "./Localisation/ja.csv",
      "assets": "./Audio/Voiceover/ja/"
    }
  },
  "definitions": "GameCommands.ysls.json"
}
```

### Working with VS Code

The Yarn Spinner VS Code extension automatically detects `.yarnproject` files in your workspace. When a project file is present:

* Only files matching `sourceFiles` patterns (minus `excludeFiles` exclusions) are compiled
* Error checking and autocompletion use the project's configuration
* Commands and functions from your `definitions` file appear in autocomplete

If no `.yarnproject` file exists in your workspace, the VS Code extension will treat all `.yarn` files in the workspace as a single implicit project.

{% hint style="info" %}
The VS Code extension does not currently respect VS Code's `files.exclude` setting. To exclude files from Yarn Spinner's compilation, use the `excludeFiles` property in your `.yarnproject` file instead.
{% endhint %}

### Troubleshooting

#### Duplicate node errors

If you're seeing "More than one node is named..." errors, you likely have duplicate `.yarn` files being compiled. This can happen when:

* Build output or cache folders contain copies of your Yarn files
* Backup folders contain older versions of files

**Solution:** Add the duplicate locations to your `excludeFiles` array:

```json
"excludeFiles": [
  "**/build/**",
  "**/backup/**",
  "**/Library/**"
]
```

#### Files not being found

If your Yarn files aren't being detected:

1. Check that your `sourceFiles` patterns are correct
2. Verify the paths are relative to the `.yarnproject` file location
3. Use the `ysc list-sources` command to see which files match your patterns

#### Verifying your configuration

Use the [Yarn Spinner Console](https://github.com/YarnSpinnerTool/YarnSpinner-Console) tool to verify which files your project includes:

```bash
ysc list-sources MyProject.yarnproject
```

This will list all Yarn files that match your `sourceFiles` patterns after applying `excludeFiles` exclusions.
