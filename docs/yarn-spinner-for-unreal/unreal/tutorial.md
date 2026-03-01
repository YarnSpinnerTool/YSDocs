---
description: Learn how to get started with Yarn Spinner in Unreal Engine 5.
---

# Unreal Quickstart

{% hint style="danger" %}
This is a Pre-release of Yarn Spinner for Unreal Engine. There will be bugs, we might change the API or features with an update, or something may break. We do not recommend you use this to ship a game just yet.&#x20;

**Please submit issues or feature requests via this form during the pre-release period:** [https://yarnspinner.dev/pre-release-feedback](https://yarnspinner.dev/pre-release-feedback)&#x20;
{% endhint %}

This gets you from zero to running dialogue in about five minutes. It assumes you already know how to write Yarn and use Unreal Engine.

{% hint style="info" %}
Yarn Spinner for Unreal Engine is not yet for sale (it will always be available here for free, too). We rely on your support to keep everything free and accessible. If you want to support us during the Pre-release period, you can support us on [GitHub Sponsors](https://github.com/sponsors/YarnSpinnerTool) or [Patreon](https://patreon.com/secretlab). GitHub sponsors of $25 and above, and Patreon members of the "Scribe" or above tier will receive a license to the paid version when it is released.
{% endhint %}

### Install the Plugin

Visit [https://github.com/YarnSpinnerTool/YarnSpinner-UnrealEngine](https://github.com/YarnSpinnerTool/YarnSpinner-UnrealEngine) to download the plugin. Then:

1. Copy the `YarnSpinner/` plugin folder into your Unreal project's `Plugins/` directory.
2. Open your project in the Unreal Editor -- the plugin will be detected automatically.

### Install ysc

The plugin needs `ysc` (the Yarn Spinner Cosole) to compile your `.yarn` files. Install the required version of it globally with:

```
dotnet tool install YarnSpinner.Console --global --version 3.1.0-alpha1
```

The editor plugin will find `ysc` automatically if it's on your PATH or in a standard dotnet tools location (`~/.dotnet/tools/`).

### Add Your Yarn Files

Create a `.yarnproject` file and your `.yarn` files. The `.yarnproject` tells the compiler which `.yarn` files to include -- the `sourceFiles` field is a list of globs or specific paths:

```json
{
  "projectFileVersion": 3,
  "sourceFiles": ["**/*.yarn"],
  "baseLanguage": "en"
}
```

This compiles every `.yarn` file in the project directory and its subdirectories. You can be more specific:

```json
{
  "sourceFiles": ["Dialogue/*.yarn", "Barks/*.yarn"]
}
```

A game can have multiple `.yarnproject` files, each pointing to different sets of `.yarn` files. Each one compiles independently into its own program -- useful for separating main story dialogue, NPC barks, tutorials, etc. Each project becomes its own `UYarnProject` asset in Unreal.

#### Import Into Unreal

Drag your `.yarnproject` file and `.yarn` files into the Content Browser. The editor plugin automatically runs `ysc compile` on it, which compiles all `.yarn` files in the project's `sourceFiles` scope into a single binary program, string table, and metadata CSV. The plugin parses those outputs and creates a `UYarnProject` asset. The temp files are cleaned up automatically.

Compilation is always the full set of source files as defined by the project -- there's no incremental or per-file compilation.

The editor plugin watches your `.yarn` files on disk. When you save a change to any `.yarn` file (or the `.yarnproject` itself), the corresponding `UYarnProject` asset is automatically reimported -- no manual action needed. Adding a new `.yarn` file that matches the project's `sourceFiles` globs also triggers automatic reimport. Rapid saves are debounced into a single reimport.

You can also reimport manually by right-clicking the asset in the Content Browser and selecting **Reimport**.

### Set Up the Actor

Here's the minimal setup:

1. **Create an actor** in your level (or use an existing one).
2. **Add a `UYarnDialogueRunner` component.** In the Details panel, set `Yarn Project` to your imported Yarn project asset.
3. **Add a `UYarnDialoguePresenter` component** (or a subclass like `UYarnWidgetPresenter`). This handles displaying lines of dialogue. Create a UMG widget for your dialogue UI and assign it.
4. **Add a `UYarnOptionsPresenter` component.** This handles showing dialogue choices. Create an option widget blueprint using `UYarnOptionWidget` as the base class, and assign it to `OptionWidgetClass`.
5. **Wire the presenters to the runner.** In the Details panel on the `UYarnDialogueRunner`, add your presenter components to the `DialoguePresenters` array.

### Start Dialogue

#### From Blueprints

Call `StartDialogue` on the dialogue runner component:

```
Dialogue Runner -> Start Dialogue ("Start")
```

Other dialogue control nodes available in Blueprints:

* **Start Dialogue** -- begin from a specific node name
* **Start Dialogue From Start** -- begin from the configured `StartNode`
* **Stop Dialogue** -- stop immediately
* **Is Dialogue Running** -- check if dialogue is active
* **Continue** -- advance to the next content
* **Request Hurry Up** -- speed up presentation (e.g., complete typewriter instantly)
* **Request Next Line** -- skip the current line entirely
* **Select Option** -- pick an option by index
* **Get Current Node Name** -- get the name of the executing node
* **Set Yarn Project** -- swap to a different Yarn project at runtime (see Runtime Project Swap)

Or tick `bAutoStart` in the Detals panel and set `StartNode` to your starting node name -- dialogue begins automatically when the game starts.

#### From C++

```cpp
UYarnDialogueRunner* Runner = MyActor->FindComponentByClass<UYarnDialogueRunner>();
Runner->StartDialogue(TEXT("Start"));
```

That's it. Run the game and your dialogue plays.

### Commands

Commands let Yarn tell your game to do things.

#### Blueprint Command Handling

The easiest way to handle commands in Blueprints is with \*_Command Handler Objects_. Add any Blueprint (or Actor, or UObject) to the dialogue runner's `Command Handler Objects` array in the Details panel. When Yarn executes a command, the runner looks for a function with the same name on those objects.

For example, if your Yarn script has:

```yarn
<<play_sound "boom">>
<<shake_camera 2.5>>
```

Create a Blueprint with functions named `play_sound` and `shake_camera`. Parameters are automatically converted from strings -- `FString`, `float`, `int`, `bool`, `FVector`, `FRotator`, etc. all work:

1. Create a new Blueprint (any UObject subclass)
2. Add a function named `play_sound` with an `FString` parameter
3. Add a function named `shake_camera` with a `float` parameter
4. Add that Blueprint to the runner's `Command Handler Objects` array

The runner auto-discovers functions matching command names. No string parsing required.

You can also bind to the **OnUnhandledCommand** event on the dialogue runner. It fires with the full command text whenever a command isn't handled by any registered handler -- useful as a catch-all.

#### C++ Lambda Registration

```cpp
DialogueRunner->AddCommandHandler(TEXT("shake"), [this](const TArray<FString>& Params)
{
    float Intensity = FCString::Atof(*Params[0]);
    CameraShake(Intensity);
});

DialogueRunner->AddCommandHandler(TEXT("fade"), [this](const TArray<FString>& Params)
{
    float Duration = FCString::Atof(*Params[0]);
    FadeToBlack(Duration);
});
```

#### Built-In Commands

The runner handles these commands automatically:

* `<<wait 2.0>>` -- pause dialogue for a duration (in seconds)
* `<<stop>>` -- end dialogue immediately

### Functions

Functions let Yarn read values from your game. Register them in C++ with a name, implementation, and parameter count:

```cpp
DialogueRunner->AddFunction(TEXT("player_health"), [this](const TArray<FYarnValue>& Params) -> FYarnValue
{
    return FYarnValue(Player->GetHealth());
}, 0);

DialogueRunner->AddFunction(TEXT("has_item"), [this](const TArray<FYarnValue>& Params) -> FYarnValue
{
    FString ItemName = Params[0].ConvertToString();
    return FYarnValue(Inventory->HasItem(ItemName));
}, 1);
```

Use them in Yarn expressions:

```yarn
<<if player_health() < 50>>
    You're not looking so good.
<<endif>>

<<if has_item("key")>>
    The door opens.
<<endif>>

You have {format("{0:F0}", player_health())} health remaining.
```

### Variables

Yarn variables work out of the box. Declare them in your `.yarn` files and they're stored in an in-memory variable storage:

```yarn
<<declare $coins = 0>>
<<declare $player_name = "Adventurer">>
<<declare $has_sword = false>>

<<set $coins = $coins + 50>>
Welcome, {$player_name}! You have {$coins} coins.
```

#### From Blueprints

The `UYarnBlueprintLibrary` provides static functions for reading and writing variables. All are available in the Blueprint action menu under **Yarn Spinner | Variables**:

**Reading variables:**

* **Get Variable As Number** -- get a float variable (returns false if not found or wrong type)
* **Get Variable As String** -- get a string variable (works for any type, converts automatically)
* **Get Variable As Bool** -- get a bool variable (returns false if not found or wrong type)
* **Has Variable** -- check if a variable exists in storage
* **Get All Variable Names** -- get an array of all variable names currently in storage
* **Get All Variables** -- get a map of all variables and their values

**Writing variables:**

* **Set Number Variable** -- set a float variable
* **Set String Variable** -- set a string variable
* **Set Bool Variable** -- set a bool variable

All of these take a `Dialogue Runner` reference and the variable name (with `$` prefix):

```
Get Variable As Number (Dialogue Runner, "$coins") -> OutValue, ReturnValue
Set Number Variable (Dialogue Runner, "$coins", 100.0)
```

**Inspecting project defaults:**

* **Get All Declared Variable Names** -- get all variables declared in a Yarn project
* **Get Declared Variable Default Value** -- get the initial value of a declared variable

#### From C++

```cpp
FYarnValue Coins;
if (DialogueRunner->GetVariableStorage()->TryGetValue(TEXT("$coins"), Coins))
{
    float CoinCount = Coins.ConvertToNumber();
}

DialogueRunner->GetVariableStorage()->SetValue(TEXT("$player_name"), FYarnValue(TEXT("Hero")));
```

The runner creates a `UYarnInMemoryVariableStorage` automatically if you don't assign one. If you need persistence, implement the `IYarnVariableStorage` interface and assign it in the Details panel.

#### Variable Change Listeners

The in-memory variable storage supports change listeners. Register a callback that fires whenever a specific variable changes:

```
Add Number Change Listener (Storage, "$coins", OnCoinsChanged)
Add String Change Listener (Storage, "$player_name", OnNameChanged)
Add Bool Change Listener (Storage, "$has_sword", OnSwordChanged)
Remove Change Listener (Handle)
```

These are `BlueprintCallable` on `UYarnInMemoryVariableStorage`. Access the storage from the runner's `VariableStorage` property.

### Save and Load Variables

The plugin provides one-call save/load functions that persist all Yarn variables to disk using Unreal's `USaveGame` system. Available in Blueprints under **Yarn Spinner | Persistence**:

* **Save Variables To Slot** -- save all variables to a named save slot
* **Load Variables From Slot** -- load variables from a save slot (clears existing variables first)
* **Does Variable Slot Exist** -- check if a save slot exists
* **Delete Variable Slot** -- delete a save slot from disk

```
Save Variables To Slot (Dialogue Runner, "YarnVariables", 0) -> bool
Load Variables From Slot (Dialogue Runner, "YarnVariables", 0) -> bool
```

The default slot name is `"YarnVariables"` and the default user index is `0`. Use different slot names for multiple save slots (e.g., `"YarnSave_Slot1"`, `"YarnSave_Slot2"`).

All three variable types (float, string, bool) are serialised. The save file is written to Unreal's standard save game directory (`Saved/SaveGames/`).

### Events

The dialogue runner fires events at key points during dialogue execution. Bind to these in Blueprints by dragging off the dialogue runner component and selecting the event:

* **On Dialogue Start** -- dialogue has begun
* **On Dialogue Complete** -- dialogue has ended
* **On Node Start** (NodeName) -- a node has started executing
* **On Node Complete** (NodeName) -- a node has finished executing
* **On Unhandled Command** (CommandText) -- a command wasn't handled by any registered handler

#### From C++

```cpp
DialogueRunner->OnDialogueStart.AddDynamic(this, &AMyActor::OnDialogueStarted);
DialogueRunner->OnDialogueComplete.AddDynamic(this, &AMyActor::OnDialogueEnded);
DialogueRunner->OnNodeStart.AddDynamic(this, &AMyActor::OnNodeEntered);
DialogueRunner->OnNodeComplete.AddDynamic(this, &AMyActor::OnNodeExited);
DialogueRunner->OnUnhandledCommand.AddDynamic(this, &AMyActor::OnCommand);
```

#### Additional Events on Other Components

**Options Presenter:**

* **On Option Selected** (OptionIndex) -- player picked an option
* **On Options Display Complete** -- options finished fading in
* **On Options Dismissed** -- options finished fading out

**Voice Over Presenter:**

* **On Voice Over Started** -- audio playback began
* **On Voice Over Complete** -- audio playback finished

**Variable Storage:**

* **On Variable Changed** (VariableName, NewValue) -- any variable was modified

### Runtime Project Swap

You can change which Yarn project a dialogue runner uses at runtime. This is useful for level transitions, DLC content, or modding support.

In Blueprints:

```
Dialogue Runner -> Set Yarn Project (NewYarnProject)
```

From C++:

```cpp
Runner->SetYarnProject(NewProject);
```

`SetYarnProject` handles all the internal state:

* Stops any active dialogue
* Updates the VM to use the new program
* Updates the line provider for localisation
* Updates variable storage's initial value lookups
* Resets presentation state

Existing variables in storage are preserved -- only the project's initial value lookups change. After swapping, call `StartDialogue` to begin running from the new project.

### Blueprint Utility Functions

The `UYarnBlueprintLibrary` class provides static functions accessible from any Blueprint. Find them in the action menu under **Yarn Spinner**.

#### Project Inspection

Query information about a Yarn project asset:

* **Get All Node Names** -- list all nodes in a project
* **Has Node** -- check if a node exists
* **Get Node Count** / **Get Line Count** -- project statistics
* **Get All Line IDs** -- list all dialogue line IDs
* **Get Node Tags** -- get tags for a specific node
* **Get All Declared Variable Names** -- list all declared variables
* **Get Declared Variable Default Value** -- get a variable's initial value

#### Finding Dialogue Runners

* **Get Dialogue Runner** (Actor) -- find the runner component on an actor
* **Get All Dialogue Runners** (WorldContext) -- find every runner in the level

#### Value Conversion

Pure functions for creating and converting `FYarnValue` structs:

* **Make Yarn Value From String/Number/Bool** -- create values
* **Yarn Value To String** -- convert any value to a display string
* **Get Yarn Value Type Name** -- get the type name ("String", "Number", "Bool")

### Useful Settings

On `UYarnDialogueRunner` in the Details panel:

* **Yarn Project** -- the imported Yarn project asset to run
* **Start Node** -- which Yarn node to begin from (default: `"Start"`)
* **Auto Start** -- begin dialogue when the game starts
* **Run Selected Option As Line** -- after the player picks an option, show it as a line of dialogue before continuing
* **Saliency Strategy** -- how to pick between competing content candidates (First, Best, BestLeastRecentlyViewed, RandomBestLeastRecentlyViewed)
* **Verbose Logging** -- log all VM execution to the output log for debugging
* **Command Handler Objects** -- array of objects with functions that match command names

On `UYarnDialoguePresenter`:

* **Auto Advance** -- automatically continue to the next line after a delay
* **Auto Advance Min/Max Delay** -- timing bounds for auto-advance
* **Auto Advance Time Per Character** -- extra delay per character in the line

On `UYarnWidgetPresenter`:

* **Typewriter Speed** -- characters per second (0 = instant)
* **Background Color** / **Text Color** / **Character Name Color** -- appearance
* **Widget Class** -- custom UMG widget class to use

On `UYarnOptionsPresenter`:

* **Option Widget Class** -- the widget Blueprint to use for each option button
* **Show Unavailable Options** -- show options the player can't pick (greyed out) instead of hiding them
* **Strikethrough Unavailable** -- draw a strikethrough on greyed-out options
* **Show Last Line** -- display the last line of dialogue above the options
* **Use Fade Effect** -- fade the options panel in/out
* **Fade In/Out Duration** -- timing for fade effects
* **Enable Keyboard Navigation** -- navigate options with arrow keys/WASD and confirm with Enter/Space
* **Navigate Up/Down Key** -- configurable navigation keys (defaults: Up/Down arrows, W/S)
* **Confirm Key** -- configurable confirm key (defaults: Enter, Space)

On `UYarnVoiceOverPresenter`:

* **End Line When Voice Over Complete** -- auto-advance when audio finishes
* **Fade Out Time On Interrupt** -- fade-out duration when interrupted
* **Wait Time Before Start** / **Wait Time After Complete** -- pre/post audio delays
* **Audio Component** -- the audio component to play through

### Custom Presenters

If the built-in presenters don't fit your UI, subclass `UYarnDialoguePresenter`.

#### In Blueprints

1. Create a new Blueprint with `UYarnDialoguePresenter` as the parent class.
2. Override **Run Line** -- this receives the localised line with character name, text, and markup. Display it however you like, then call **On Line Presentation Complete** when done.
3. Override **Run Options** -- this receives the option set. Display the options, then call **On Option Selected** with the chosen index.
4. Optionally override **On Dialogue Started**, **On Dialogue Complete**, **On Node Enter**, **On Node Exit**, **On Hurry Up Requested**, **On Next Line Requested**, and **On Prepare For Lines**.

The `FYarnLocalizedLine` struct passed to `RunLine` contains:

* `Text` -- the final localised text
* `CharacterName` -- extracted character name (from "Name: text" format)
* `TextWithoutCharacterName` -- text with the character name prefix removed
* `Metadata` -- array of line tags (from `#tag` syntax in Yarn)
* `TextMarkup` -- parsed markup attributes for effects like `[bold]`, `[shake]`, etc.
* `RawLine` -- the original line data including LineID and substitutions

#### In C++

```cpp
UCLASS(Blueprintable)
class UMyPresenter : public UYarnDialoguePresenter
{
    GENERATED_BODY()

public:
    virtual void RunLine_Implementation(const FYarnLocalizedLine& Line, bool bCanHurry) override
    {
        // Display the line however you want
        UE_LOG(LogTemp, Log, TEXT("%s: %s"), *Line.CharacterName, *Line.Text);

        // Call this when you're done presenting the line
        OnLinePresentationComplete();
    }

    virtual void RunOptions_Implementation(const FYarnOptionSet& Options) override
    {
        // Build your own UI, then call OnOptionSelected(index) when the player picks one
        for (int32 i = 0; i < Options.Options.Num(); i++)
        {
            UE_LOG(LogTemp, Log, TEXT("  [%d] %s"), i, *Options.Options[i].Line.Text);
        }
    }
};
```

Register it the same way: add it to the `DialoguePresenters` array on the dialogue runner.

#### Custom Option Widgets

Subclass `UYarnOptionWidget` to customise option button appearance. Override these Blueprint events:

* **Setup Option** -- initialise the widget with option data and index
* **Set Option Unavailable** -- style the widget as unavailable
* **On Option Selected** -- the option was highlighted/focused
* **On Option Deselected** -- the option lost focus

The widget has `OptionText` (UTextBlock) and `OptionButton` (UButton) as bound widgets. Add them to your UMG widget and the base class wires them up.

### Node Groups and Saliency

If you're using node groups (multiple versions of the same content with `when:` conditions), set a saliency strategy on the runner in the Details panel. Available strategies:

* **First** -- pick the first viable candidate
* **Best** -- pick the most specific (highest complexity) viable candidate
* **BestLeastRecentlyViewed** -- pick the most specific candidate that hasn't been seen recently
* **RandomBestLeastRecentlyViewed** -- like above, but randomised among equally-good candidates (this is the default)

### Localisation

The built-in line provider (`UYarnBuiltinLineProvider`) supports full localisation. Key properties (all configurable in Details panel or from Blueprints):

* **Auto Detect Culture** -- automatically use the system's locale
* **Text Locale Code** -- manually set the locale (e.g., `"fr"`, `"de"`, `"ja"`)
* **Use Fallback** -- fall back to another locale if a translation is missing
* **Fallback Locale Code** -- the fallback locale (default: base language)

Blueprint functions on the line provider:

* **Get Locale Code** -- get the current locale
* **Set Locale Code** -- change the locale at runtime
* **Get Available Locales** -- list all locales that have translations
* **Add Localized String** -- add a runtime localised string for a line ID and locale

### Voice Over

Add a `UYarnVoiceOverPresenter` component to play audio synced to dialogue lines. It looks up `USoundBase` assets by line ID and plays them through a `UAudioComponent`. Configure the base content path and it handles the rest -- fade-in, fade-out, and interruption are all built in.

Override `GetVoiceOverClip` in a Blueprint subclass to customise how audio assets are resolved.

### Debug HUD

Add a `UYarnDebugHUDComponent` to your actor to get a real-time debug overlay showing:

* Current node and line ID
* All variables and their values
* Execution history (lines, options selected, commands, node transitions)

Configure in the Details panel:

* **Dialogue Runner** -- which runner to monitor
* **Toggle Key** -- key to show/hide the HUD (default: F3)
* **Show By Default** -- whether to show the HUD on start
* **Auto Log Events** -- automatically log dialogue events to the history
* **Screen Anchor** -- position on screen (0,0 = top-left, 1,1 = bottom-right)

You can also use the `UYarnDebugWidget` directly in your own UMG layouts.

### Markup

The plugin supports Yarn's full markup system. Tags in your dialogue text are parsed and made available to presenters:

```yarn
I [bold]really[/bold] need your help with [shake]this[/shake]!
You need {format("{0:N0}", $coins)} coins.    // thousand separators
I have [plural value={$apples} one="% apple" other="% apples"/].
```

Register custom markup processors by implementing the `IYarnMarkupProcessor` interface, or use the built-in `UYarnPaletteMarkupProcessor` with a `UYarnRichTextPalette` data asset to define styles in the editor without writing code.
