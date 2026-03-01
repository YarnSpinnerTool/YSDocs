# Unreal

{% hint style="danger" %}
Yarn Spinner for Unreal is in Pre-release now.
{% endhint %}

Yarn Spinner for Unreal Engine is a pure-C++ implementation of the Yarn Spinner dialogue system for Unreal Engine. It runs compiled Yarn programs with the goal of full feature parity with Yarn Spinner for Unity, including node groups, saliency, detours, smart variables, localisation, markup, and voice over support.

The entire plugin is intended to be Blueprint-accessible. You can set up dialogue, handle commands, read/write variables, save/load state, swap projects at runtime, and build custom presenters entirely from Blueprints with no C++ required.

A sample project will be coming soon, during the pre-release period!

Requires Unreal Engine 5.4 or later. If you want to use Yarn Spinner for Unreal Engine with an earlier version of Unreal Engine, please contact us via https://yarnspinner.dev

{% hint style="danger" %}
Yarn Spinner for Unreal Engine is not yet for sale (it will always be available here for free, too). We rely on your support to keep everything free and accessible. If you want to support us during the Alpha period, you can support us on [GitHub Sponsors](https://github.com/sponsors/YarnSpinnerTool) or [Patreon](https://patreon.com/secretlab). GitHub sponsors of $25 and above, and Patreon members of the "Scribe" or above tier will receive a license to the paid version when it is released.
{% endhint %}

{% hint style="info" %}
**Please submit issues or feature requests via this form during the pre-release period:** [https://yarnspinner.dev/pre-release-feedback](https://yarnspinner.dev/pre-release-feedback)
{% endhint %}

### Differences from Yarn Spinner for Unity

The VM, protobuf parser, library, and markup system were all written to match Unity's behaviour, but there are some differences:

* **CLDR plural rules** -- Unity includes the full Unicode CLDR v42.0 database (\~150 languages). This implementation has rules covering \~130 languages. Coverage is comprehensive, but if you're using `[plural]` or `[ordinal]` markup tags with a some languages, you might get the default "one/other" fallback instead of the correct plural form.
* **No Unicode NFC normalisation** -- Unity normalises markup input text to NFC (composed) form before parsing. Unreal doesn't have a built-in NFC normaliser, so precomposed and decomposed Unicode characters are treated as-is. This only matters if your Yarn scripts contain combining characters like `e` + `\u0301` instead of `é`.
* **Async model** -- Unity uses C# `async`/`await` with `YarnTask` and `CancellationTokenSource` chains. This implementation uses Unreal delegates and a two-tier `UYarnCancellationToken` system (hurry-up then next-content). The behaviour is the same, but the presenter API uses UE-idiomatic patterns instead of tasks.
* **Command discovery** -- Unity uses `[YarnCommand]` attributes on methods. This implementation uses Blueprint-callable `UFUNCTION` methods on registered command handler objects, plus a C++ `AddCommandHandler` API. Both approaches register commands, just with diffeent syntax.
* **Error handling** -- Unity throws exceptions for invalid states (missing variables, bad option indices, etc.). This implementation uses `UE_LOG` warnings/errors and defensive fallbacks where possible, which is more idiomatic for Unreal Engine.
* **Localisation** -- Unity has multiple line provider backends (built-in, Unity Localization package, Addressables). This implementation uses Unreal's `FText` and string table system. You can subclass the line provider to plug in your own localisation pipeline.
* **Blueprint support** -- This implementation exposes the full dialogue system to Blueprints. Every component is Blueprintable, every control method is BlueprintCallable, all events are BlueprintAssignable, and presenter methods are BlueprintNativeEvent. A `UYarnBlueprintLibrary` provides 30+ static utility functions. See Blueprint Support for details.
* **Persistence** -- Unity has `SaveStateToPersistentStorage`/`LoadStateFromPersistentStorage`. This implementation provides `SaveVariablesToSlot`/`LoadVariablesFromSlot` via `UYarnBlueprintLibrary`, using Unreal's native `USaveGame` system.

### License

This project uses the Yarn Spinner Public License. You're free to use it in your own projects, commercial or otherwise. The only restrictions are around redistributing it as part of a competing dialogue tool, and using it to train AI models. Full details are in LICENSE.md.

### Installation

1. Copy the `YarnSpinner/` folder from this repository into your Unreal project's `Plugins/` directory (so that `YarnSpinner.uplugin` is at `Plugins/YarnSpinner/YarnSpinner.uplugin`).
2. Open your project in the Unreal Editor -- the plugin will be detected automatically.
3. Install `ysc` (the [Yarn Spinner Console](https://github.com/YarnSpinnerTool/YarnSpinner-Console) tool) from : `dotnet tool install YarnSpinner.Console --global --version 3.1.0-alpha1`
4. Write your dialogue in `.yarn` files. Create a `.yarnproject` file that defines which `.yarn` files to include via `sourceFiles` globs.
5. Drag your `.yarnproject` into the Content Browser. The plugin automatically runs `ysc compile`, parses the compiled program, string table, and metadata, and creates a `UYarnProject` asset.
6. Add a `UYarnDialogueRunner` component to an actor, assign your imported Yarn Project asset, and call `StartDialogue()`.

A game can have multiple `.yarnproject` files, each with its own `sourceFiles` scope -- useful for separating story dialogue, NPC barks, tutorials, etc. Each one compiles independently into its own `UYarnProject` asset.

### How It Works

The Yarn Spinner compiler (`ysc`) compiles a `.yarnproject` and all `.yarn` files in its `sourceFiles` scope into a single binary (`.yarnc`), a string table CSV, and a metadata CSV. The editor plugin runs `ysc` automatically at import time via a custom `UFactory`, parses the outputs into an in-memory program representation (`UYarnProgram`), and cleans up the temp files. At runtime, a stack-based virtual machine executes the program. The VM handles control flow, variable storage, function calls, saliency selection, and content delivery. A dialogue runner component orchestrates the VM and routes lines, options, and commands to presenter components in your scene.

Compilation is always the full set of source files as defined by the project -- there's no incremental or per-file compilation. The editor plugin watches your `.yarn` source files on disk and automatically reimports the associated `UYarnProject` asset when any change is detected -- edits, new files, or changes to the `.yarnproject` itself. Rapid saves are debounced into a single reimport. You can also reimport manually via right-click in the Content Browser.

You write dialogue in Yarn, drag in the `.yarnproject`, and the plugin handles compilation, file watching, and everything else.

### Architecture

The plugin has three layers:

**Core** (`Source/YarnSpinner/`) contains the runtime engine. The protobuf parser reads compiled `.yarnproject` binaries. The virtual machine (`FYarnVirtualMachine`) executes instructions. The built-in library provides operators and functions (arithmetic, comparisons, `visited`, `random_range`, `format`, etc.). Variable storage (`IYarnVariableStorage`) holds game state. The markup parser applies CLDR plural rules, `[select]`/`[plural]`/`[ordinal]` replacement markers, and the adoption agency algorithm for nested tags. The saliency system selects content when multiple candidates match. The smart variable evaluation VM resolves computed variables.

**Dialogue Runner** (`UYarnDialogueRunner`) is the main component you add to your actor. It owns the VM, registers built-in functions, discovers commands from handler objects, coordinates presenters, and exposes delegates for dialogue lifecycle events (`OnDialogueStart`, `OnNodeStart`, `OnNodeComplete`, `OnDialogueComplete`, `OnUnhandledCommand`). All configuration is done through its `UPROPERTY` fields in the Details panel. Every control method is BlueprintCallable and every event is BlueprintAssignable.

**Presenters** display content to the player. `UYarnDialoguePresenter` is the base class -- it delivers lines with typewriter animation and handles the hurry-up/next-content cancellation flow. `UYarnOptionsPresenter` shows dialogue choices. `UYarnVoiceOverPresenter` plays audio files synced to lines. `UYarnWidgetPresenter` manages UMG widgets for dialogue UI. All presenters are Blueprintable -- subclass them in Blueprints and override `RunLine`, `RunOptions`, and other events without writing C++.

### Blueprint Support

The plugin is designed for Blueprint-first development. Every component, method, and event is accessible from Blueprints.

#### What You Can Do From Blueprints (No C++ Required)

**Dialogue control** -- start, stop, pause, and resume dialogue. Check if dialogue is running. Get the current node name. Swap Yarn projects at runtime.

**Command handling** -- add any Blueprint to the runner's `CommandHandlerObjects` array. Functions matching command names are discovered and called automatically with type-converted parameters. No string parsing needed.

**Variable access** -- read and write Yarn variables by name. Get/set typed values (string, float, bool). List all variables. Check if a variable exists. Listen for variable changes with callbacks.

**Save/load** -- one-call save and load of all Yarn variables to disk via Unreal's `USaveGame` system. Manage save slots (check existence, delete).

**Runtime project swap** -- change which Yarn project a runner uses at runtime via `SetYarnProject`. Useful for level transitions, DLC, or modding.

**Custom presenters** -- subclass `UYarnDialoguePresenter` in Blueprints and override `RunLine` and `RunOptions` to build custom dialogue UI without any C++.

**Custom option widgets** -- subclass `UYarnOptionWidget` to customise option button appearance. Override `SetupOption`, `SetOptionUnavailable`, `OnOptionSelected`, `OnOptionDeselected`.

**Event binding** -- bind to `OnDialogueStart`, `OnDialogueComplete`, `OnNodeStart`, `OnNodeComplete`, `OnUnhandledCommand`, `OnVariableChanged`, `OnOptionSelected`, `OnVoiceOverStarted`, `OnVoiceOverComplete`.

**Localisation** -- change locale at runtime, query available locales, add runtime localised strings.

**Project inspection** -- query node names, line IDs, tags, variable declarations, and project statistics from Blueprints.

**Debug overlay** -- add a `UYarnDebugHUDComponent` for a real-time debug display showing variables, execution history, and current dialogue state. Toggle with a configurable key.

#### UYarnBlueprintLibrary

A static function library providing 30+ utility functions accessible from any Blueprint. All functions appear under **Yarn Spinner** in the action menu.

| Category               | Functions                                                                                                                                                                               |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Project Inspection** | `GetAllNodeNames`, `HasNode`, `GetNodeCount`, `GetLineCount`, `GetAllLineIDs`, `GetNodeTags`, `GetAllDeclaredVariableNames`, `GetDeclaredVariableDefaultValue`                          |
| **Variable Access**    | `GetAllVariableNames`, `GetAllVariables`, `HasVariable`, `GetVariableAsString`, `GetVariableAsNumber`, `GetVariableAsBool`, `SetStringVariable`, `SetNumberVariable`, `SetBoolVariable` |
| **Persistence**        | `SaveVariablesToSlot`, `LoadVariablesFromSlot`, `DoesVariableSlotExist`, `DeleteVariableSlot`                                                                                           |
| **Value Conversion**   | `MakeYarnValueFromString`, `MakeYarnValueFromNumber`, `MakeYarnValueFromBool`, `YarnValueToString`, `GetYarnValueTypeName`                                                              |
| **Runner Helpers**     | `GetDialogueRunner` (find on actor), `GetAllDialogueRunners` (find all in level)                                                                                                        |

### Components

#### UYarnDialogueRunner

The central component. Add it to an actor, assign a Yarn Project asset, and call `StartDialogue()`.

**Configuration properties** (all editable in Details panel):

* `YarnProject` (BlueprintReadOnly) -- the imported Yarn project asset to run
* `StartNode` (BlueprintReadWrite) -- which node to begin from (default: `"Start"`)
* `bAutoStart` (BlueprintReadWrite) -- start dialogue when the game begins
* `VariableStorage` (BlueprintReadWrite) -- where game state is stored (auto-created if not set)
* `DialoguePresenters` (BlueprintReadWrite) -- array of presenter components that receive lines and options
* `LineProvider` (BlueprintReadWrite) -- localisation provider (auto-created if not set)
* `CommandHandlerObjects` (BlueprintReadWrite) -- array of objects with functions matching command names
* `SaliencyStrategy` (BlueprintReadWrite) -- how to pick between competing content candidates
* `bRunSelectedOptionAsLine` (BlueprintReadWrite) -- re-display the chosen option as a line of dialogue
* `bVerboseLogging` (BlueprintReadWrite) -- log all VM execution for debugging

**BlueprintCallable methods:**

* `SetYarnProject` -- swap to a different Yarn project at runtime
* `StartDialogue` / `StartDialogueFromStart` -- begin dialogue
* `StopDialogue` -- stop immediately
* `IsDialogueRunning` -- check if active
* `Continue` -- advance to next content
* `RequestHurryUp` / `RequestNextLine` / `RequestHurryUpOption` -- cancellation flow
* `SelectOption` -- pick an option by index
* `GetCurrentNodeName` -- get executing node name
* `GetCurrentCancellationToken` / `GetCurrentOptionsCancellationToken` -- for presenter use

**BlueprintAssignable events:**

* `OnDialogueStart` -- dialogue has begun
* `OnDialogueComplete` -- dialogue has ended
* `OnNodeStart` (NodeName) -- a node started executing
* `OnNodeComplete` (NodeName) -- a node finished executing
* `OnUnhandledCommand` (CommandText) -- unhandled command received

#### UYarnDialoguePresenter

Base presenter class for displaying dialogue lines. Handles typewriter-style text reveal with configurable speed (letters per second), auto-advance timing, and the two-tier cancellation system (hurry-up reveals text instantly, next-content advances to the next line). Supports character name extraction and markup-processed text.

**BlueprintNativeEvent methods** (override in Blueprint subclasses):

* `RunLine` (Line, bCanHurry) -- display a line of dialogue. **Must** call `OnLinePresentationComplete` when done.
* `RunOptions` (Options) -- display dialogue choices. **Must** call `OnOptionSelected(Index)` when the player picks one.
* `OnDialogueStarted` / `OnDialogueComplete` -- dialogue lifecycle
* `OnNodeEnter` / `OnNodeExit` (NodeName) -- node lifecycle
* `OnHurryUpRequested` / `OnNextLineRequested` -- cancellation events
* `OnOptionsHurryUpRequested` -- option cancellation
* `OnPrepareForLines` (LineIDs) -- pre-load upcoming lines

**BlueprintCallable methods:**

* `OnLinePresentationComplete` -- signal that line presentation is done
* `OnOptionSelected` (Index) -- signal that an option was chosen
* `SetAutoAdvanceEnabled` / `IsAutoAdvanceEnabled` -- auto-advance control
* `StartAutoAdvanceTimer` / `CancelAutoAdvanceTimer` -- timer management
* `GetDialogueRunner` -- get the owning runner
* `IsHurryUpRequested` / `IsNextContentRequested` -- check cancellation state

**BlueprintReadOnly state:**

* `bIsPresentingLine` / `bIsPresentingOptions` -- current presentation state
* `CurrentLine` / `CurrentOptions` -- current content being presented

#### UYarnWidgetPresenter

Ready-to-use text presenter that creates and manages a UMG widget. Handles typewriter effects with configurable speed.

* `TypewriterSpeed` (BlueprintReadWrite) -- characters per second (0 = instant)
* `BackgroundColor` / `TextColor` / `CharacterNameColor` (BlueprintReadWrite) -- appearance
* `WidgetClass` (BlueprintReadWrite) -- custom widget class
* `GetDialogueWidget()` (BlueprintCallable) -- get the widget instance

#### UYarnOptionsPresenter

Shows dialogue choices. Receives an option set from the runner, creates UI for each option, handles selection via mouse/keyboard/gamepad, and reports the selected option back.

**Configuration** (all BlueprintReadWrite):

* `OptionWidgetClass` -- the option button widget class
* `OptionsContainer` -- panel to add option widgets to
* `bShowUnavailableOptions` / `bStrikethroughUnavailable` -- unavailable option display
* `bShowLastLine` -- show the last line above options
* `bUseFadeEffect` / `FadeInDuration` / `FadeOutDuration` -- fade effects
* `bEnableKeyboardNavigation` -- keyboard/gamepad navigation
* `NavigateUpKey` / `NavigateDownKey` / `ConfirmKey` (and alternates) -- configurable keys

**BlueprintCallable methods:**

* `SelectOptionByIndex` / `SelectNextOption` / `SelectPreviousOption` -- navigation
* `ConfirmSelectedOption` -- confirm selection
* `GetSelectedOptionIndex` / `AreOptionsVisible` -- query state

**BlueprintAssignable events:**

* `OnOptionSelected` (OptionIndex)
* `OnOptionsDisplayComplete` / `OnOptionsDismissed`

#### UYarnOptionWidget

Individual option button widget. Subclass in Blueprints to customise appearance.

**BlueprintNativeEvent methods:**

* `SetupOption` (Option, Index) -- initialise with option data
* `SetOptionUnavailable` -- style as unavailable
* `OnOptionSelected` / `OnOptionDeselected` -- focus state

**Bound widgets** (add these to your UMG widget):

* `OptionText` (UTextBlock, BindWidget)
* `OptionButton` (UButton, BindWidget)

#### UYarnVoiceOverPresenter

Plays audio files synced to dialogue lines. Looks up audio assets by line ID and plays them through a `UAudioComponent`. Supports fade-in/fade-out and interruption.

* `bEndLineWhenVoiceOverComplete` (BlueprintReadWrite) -- auto-advance on audio end
* `FadeOutTimeOnInterrupt` / `WaitTimeBeforeStart` / `WaitTimeAfterComplete` (BlueprintReadWrite) -- timing
* `AudioComponent` (BlueprintReadWrite) -- audio component to use
* `GetVoiceOverClip` (BlueprintNativeEvent) -- override to customise audio lookup
* `OnVoiceOverStarted` / `OnVoiceOverComplete` (BlueprintAssignable) -- events

#### UYarnInMemoryVariableStorage

Default variable storage. Stores variables in a `TMap`. Implements the `IYarnVariableStorage` interface.

**BlueprintCallable methods:**

* `SetString` / `SetNumber` / `SetBool` / `SetValue` -- set variables (BlueprintNativeEvent)
* `TryGetValue` / `Contains` -- read variables (BlueprintNativeEvent)
* `Clear` -- remove all variables (BlueprintNativeEvent)
* `GetAllVariables` -- get all variables as typed maps (float, string, bool)
* `SetAllVariables` -- restore from typed maps (with optional clear)
* `GetAllVariablesAsMap` -- get all as a single FYarnValue map
* `GetDebugString` -- formatted debug output
* `AddStringChangeListener` / `AddNumberChangeListener` / `AddBoolChangeListener` -- per-variable callbacks
* `RemoveChangeListener` -- remove a callback
* `RegisterSmartVariableEvaluator` / `UnregisterSmartVariableEvaluator` -- smart variable support

**BlueprintAssignable events:**

* `OnVariableChanged` (VariableName, NewValue)

#### UYarnBuiltinLineProvider

Full localisation support. Auto-detects system culture, supports fallback locales.

* `bAutoDetectCulture` / `TextLocaleCode` (BlueprintReadWrite) -- locale configuration
* `bUseFallback` / `FallbackLocaleCode` (BlueprintReadWrite) -- fallback configuration
* `GetLocaleCode` / `SetLocaleCode` (BlueprintCallable) -- runtime locale control
* `GetAvailableLocales` (BlueprintCallable) -- list available translations
* `AddLocalizedString` (BlueprintCallable) -- add runtime translations

#### UYarnDebugHUDComponent

Debug overlay for monitoring dialogue state at runtime.

* `DialogueRunner` (BlueprintReadWrite) -- runner to monitor
* `DebugWidgetClass` (BlueprintReadWrite) -- custom debug widget class
* `ToggleKey` (BlueprintReadWrite) -- key to show/hide (default: F3)
* `bShowByDefault` (BlueprintReadWrite) -- show at start
* `bAutoLogEvents` (BlueprintReadWrite) -- auto-log dialogue events
* `ScreenAnchor` (BlueprintReadWrite) -- position on screen
* `ToggleDebugHUD` / `ShowDebugHUD` / `HideDebugHUD` / `IsDebugHUDVisible` (BlueprintCallable)

#### Custom Commands

Commands can be handled three ways:

**1. Blueprint Command Handler Objects** (recommended for Blueprints) -- Add any UObject to the runner's `CommandHandlerObjects` array. Create functions matching command names. Parameters auto-convert from strings to the function's parameter types (`FString`, `float`, `int`, `bool`, `FVector`, `FRotator`, etc.).

**2. C++ Lambda Registration:**

```cpp
DialogueRunner->AddCommandHandler(TEXT("shake"), [this](const TArray<FString>& Params)
{
    float Intensity = FCString::Atof(*Params[0]);
    // shake the camera
});
```

**3. OnUnhandledCommand event** -- catch-all for commands not handled by methods 1 or 2. Fires with the full command text string.

From Yarn:

```yarn
<<shake 2.5>>
<<fade 1.0>>
```

#### Localisation

Localisation uses the Yarn Spinner compiler's CSV string table export. The compiler generates a `-Lines.csv` file containing all line IDs and their text. Translate the CSV, reimport, and the plugin resolves localised text at runtime through the line provider. The built-in line provider supports auto-detection of system culture, manual locale override, and fallback locales -- all configurable from Blueprints at runtime.

#### Voice Over

The `UYarnVoiceOverPresenter` component plays audio assets matched to dialogue line IDs. Place your audio files in a content directory structure that maps to line IDs, configure the presenter with the base path, and it will automatically find and play the right audio for each line. Supports `USoundBase` assets (wav, ogg, etc.). Override `GetVoiceOverClip` in a Blueprint subclass for custom audio resolution.
