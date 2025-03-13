# Variable Storage

Variable Storage components are responsible for storing and retrieving the values of variables in your Yarn scripts. When a Yarn script needs to get the value of a variable, it asks the Variable Storage for it; when a Yarn script sets the value of a variable, the Variable Storage is given the value.

Each game has different requirements for how variables are stored, which means that Yarn Spinner doesn't make any assumptions how the information is actually stored on disk. Instead, you can create your own custom Variable Storage script that implements the methods that Yarn Spinner needs.

{% hint style="info" %}
If you don't have a game save system, you can use the [In-Memory Variable Storage](../../../yarn-spinner-for-godot/components/variable-storage/in-memory-variable-storage.md) component. This is a simple Variable Storage component that's built into Yarn Spinner.

The In-Memory Variable Storage stores everything in memory; when the game ends, all variables that have been stored are erased.
{% endhint %}

If you don't connect a Variable Storage to your Dialogue Runner, it will create an In-Memory Variable Storage when the game starts, and use that.
