---
description: Learn about Yarn Spinner Project files.
icon: file
---

# Yarn Spinner Project Files

{% hint style="warning" %}
You shouldn't need to think about most of this. If you're starting a project in a game engine, then working on your Yarn Scripts, there is likely to be a Yarn Spinner Project file already present.
{% endhint %}

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
  "projectFileVersion": 4,
<strong>  "sourceFiles": ["**/*.yarn"],
</strong>  },
}
</code></pre>

The Yarn Spinner VS Code extension automatically detects `.yarnproject` files in your workspace. When a project file is present:

* Only files matching `sourceFiles` patterns (minus `excludeFiles` exclusions) are compiled
* Error checking and autocompletion use the project's configuration
* Commands and functions from your `definitions` file appear in autocomplete

If no `.yarnproject` file exists in your workspace, the VS Code extension will treat all `.yarn` files in the workspace as a single implicit project.

{% hint style="info" %}
The VS Code extension does not currently respect VS Code's `files.exclude` setting. To exclude files from Yarn Spinner's compilation, use the `excludeFiles` property in your `.yarnproject` file instead.
{% endhint %}

You can review the schemas for the Yarn Project (and other elements of Yarn Spinner) here: [https://schemas.yarnspinner.dev/](https://schemas.yarnspinner.dev/)

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
