# Variable Storage

Variable Storage components are responsible for storing and retrieving the values of variables in your Yarn scripts. When a Yarn script needs to get the value of a variable, it asks the Variable Storage for it; when a Yarn script sets the value of a variable, the Variable Storage is given the value.

Each game has different requirements for how variables are stored, which means that Yarn Spinner doesn't make any assumptions how the information is actually stored on disk. Instead, you can create your own custom Variable Storage script that implements the methods that Yarn Spinner needs.

{% hint style="info" %}
If you don't have a game save system, you can use the [`MemoryVariableStorage`](https://docs.rs/yarnspinner/latest/yarnspinner/runtime/struct.MemoryVariableStorage.html) component. This is a simple Variable Storage component that's built into Yarn Spinner.

The In-Memory Variable Storage stores everything in memory; when the game ends, all variables that have been stored are erased.
{% endhint %}

If you don't connect a Variable Storage to your Dialogue Runner, it will create an In-Memory Variable Storage when the game starts, and use that.

## In-Memory Variable Storage

The In-Memory Variable Storage component is a Variable Storage component that stores all variables in memory. These variables are erased when the game stops.

{% hint style="info" %}
The In-Memory Variable Storage component is intended to be a useful tool for getting started, and to be replaced with a custom variable storage that meets your game's needs.

However, if your game has no need to save and restore game state, then this class can be used in your final game, too.
{% endhint %}

## Custom Variable Storages

Every game's data storage requirements are different. For this reason, Yarn Spinner is designed to make it straightforward to create your own custom component for managing how Yarn scripts store and load variables in ways that work with the other parts of your game.

Custom Variable Storage components are implementations of the trait [`VariableStorage`](https://docs.rs/yarnspinner/latest/yarnspinner/prelude/trait.VariableStorage.html). To implement your own, check out the documentation. Once you have it, you can use it by calling [`DialogueRunnerBuilder::with_variable_storage`](https://docs.rs/bevy_yarnspinner/latest/bevy_yarnspinner/prelude/struct.DialogueRunnerBuilder.html#method.with_variable_storage) when building your Dialogue Runner.
