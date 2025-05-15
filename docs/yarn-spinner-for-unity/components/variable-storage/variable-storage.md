---
description: This guide teaches you how to use the Variable Storage system.
---

# Variable Storage

Variables form the foundation of any programming language, and Yarn Spinner is no exception. While Yarn Spinner manages variables differently than you might be accustomed to, understanding this system becomes increasingly important as your games grow in complexity.

This guide explores Yarn Spinner's variable storage system in two parts: first examining how to get the most from the provided system, then diving into more advanced implementation of custom variable storage solutions.

### What We'll Be Covering

* Using the variable storage system from your Unity code
* Reading and writing variables via C#
* Generated variable storage wrappers
* Using the in-memory variables storage system
* Making your own Variable Storage systems

### Yarn Variables

Yarn Spinner deliberately limits variable types to strings, numbers, booleans, and enumerations (which themselves are wrappers around the first three types). At its core, Yarn Spinner isn't actually concerned with variables themselves, but rather with _values_. When encountering a variable, all Yarn Spinner needs is a way to replace that variable with its corresponding value.

This creates an interesting challenge: while computers handle changing values with ease, humans struggle to track unnamed values. Our brains naturally organize information through naming conventions. Variables bridge this gap by giving changeable values names that we can easily reference and understand.

This is where the Variable Storage system comes into play. It handles the translation between human-friendly named variables and computer-friendly values. The system performs this crucial mapping function, while most of Yarn Spinner simply asks "what's the value of `$gold`?" without concerning itself with how that value is stored or managed.

### Using the Variable Storage

Every game has unique requirements for variable handling. Since Yarn Spinner can't anticipate your specific storage methods, it uses a common interface to get and set variables. This interface connects to your game through the Dialogue Runner.

The Dialogue Runner includes a `VariableStorage` property that anything with a reference to the runner can access. When using a custom variable storage system, setting this property configures Yarn Spinner to use your implementation. If you don't provide a variable storage system, Yarn Spinner creates a temporary one automatically.

For beginners, we recommend letting Yarn Spinner handle variable storage temporarily. As your project grows, you'll likely want to implement a more permanent, game-specific storage solution.

#### Accessing Yarn Variables in your Code

While using variables within Yarn scripts is straightforward, accessing them from C# requires a few additional steps. Because the variable storage system is designed to be replaceable, Yarn Spinner uses the same approaches we'll explore here to interact with variables.

**Reading Yarn Variables**

To read a Yarn variable in C#, you'll need a reference to your game's dialogue runner. Through this reference, you can access the variable storage system:

```csharp
// getting the dialogue runner
var runner = FindObjectOfType<Yarn.Unity.DialogueRunner>();
if (runner == null)
{
    Debug.LogWarning("Was unable to find a dialogue runner");
    return;
}

// attempting to find a float called $gold
if (runner.VariableStorage.TryGetValue<float>("$gold", out var gold))
{
    // we found the variable
    // it's value has been stored into the gold parameter
    // we can now use the gold variable
    if (gold > 100)
    {
        Debug.Log("they are rich, unlock the Player Is Rich cheevo!");
    }
}
else
{
    // we failed to find $gold
    Debug.LogWarning("Was unable to find a number value for $gold");
}
```

The variable storage's `TryGetValue` method returns a boolean indicating whether the variable was found. A `true` result means a variable with the specified name and type was located and stored in the output parameter. A `false` result indicates failure to find a matching variable, so check your spelling and requested type when troubleshooting.

**Writing Yarn Variables**

Similarly, setting variables uses the dialogue runner's variable storage as the entry point:

```csharp
// getting the dialogue runner
var runner = FindObjectOfType<Yarn.Unity.DialogueRunner>();
if (runner == null)
{
    Debug.LogWarning("Was unable to find a dialogue runner");
    return;
}

// modifying the value of the players gold, they now have 25 gold
runner.VariableStorage.SetValue("$gold", 25);
```

#### Generated Wrapper

While the methods above work effectively, they're not particularly convenient. Yarn Spinner v3 introduces a more elegant solution: a generated wrapper around your variable storage that provides direct property access to each variable.

For example, if your Yarn script includes:

```yarn
/// the number of gold coins the player has
<<declare $gold = 0>>
```

The generator would create:

```csharp
/// <summary>
/// the number of gold coins the player has
/// </summary>
public float Gold
{
    get
    {
        if (this.TryGetValue<float>("$gold", out var gold))
        {
            return gold;
        }
        return 0;
    }
    set => this.SetValue<float>("$gold", value);
}
```

This approach eliminates the need to write wrapper code manually. It also handles enumerations, generating C# versions of any enums declared in your Yarn scripts. For example:

```yarn
<<enum TimeOfDay>>
    <<case Morning>>
    <<case Evening>>
<<endenum>>
```

Becomes:

```csharp
public enum TimeOfDay
{
    /// <summary>
    /// Morning
    /// </summary>
    Morning = 0,

    /// <summary>
    /// Evening
    /// </summary>
    Evening = 1,
}
```

The system also preserves any custom backing values you define for your enums.

**Making a generated storage wrapper**

To generate a variable storage wrapper, start with your Yarn Project:

1. In the Inspector, check the `Generate Variables Source File` box
2. Enter a class name
3. Specify a namespace
4. Select the parent class for your variable storage
5. Click the `Apply` button

![A generated variable storage settings](<../../../.gitbook/assets/01 (1).png>)

This creates a new C# file containing your wrapper class. Remember to connect this variable storage to your dialogue runner before using it.

#### In-Memory Variable Storage

Yarn Spinner's built-in in-memory variable storage works well for development projects and smaller games. It wraps a standard dictionary and is automatically created if you don't provide your own storage system.

Its primary limitation is ephemerality—variables only exist as long as they remain in memory. When a scene unloads or the game closes, any unsaved changes are lost. The system does support persistence through the dialogue runner's `SaveStateToPersistentStorage` and `LoadStateFromPersistentStorage` methods, but you must call these explicitly at appropriate times.

The saving process collects all variables from storage, converts them to a JSON string, and writes this data to a file in Unity's persistent data folder. The specific location [varies by operating system](https://docs.unity3d.com/6000.0/Documentation/ScriptReference/Application-persistentDataPath.html), but provides a safe space for save data.

Loading performs this process in reverse, reading the JSON string and injecting the recovered variables back into storage. Remember that players can access and potentially delete save files, so your code should handle missing files gracefully.

While the in-memory storage with built-in saving/loading works adequately for smaller projects, it typically won't scale to meet the needs of larger games. For those situations, you'll want to implement a custom variable storage solution.

### Making your own Variable Storage System

Larger games typically already have established systems for managing game state and handling save/load functionality. Rather than maintaining separate systems for Yarn variables, why not integrate them into your existing architecture? This provides a single source of truth for all game data, simplifying development and maintenance.

To make your existing state system compatible with Yarn Spinner, you'll need to implement a `VariableStorageBehaviour` subclass. This MonoBehaviour implements interfaces that allow Yarn Spinner to interact with your storage system.

You'll need to implement eight key methods, starting with these four for individual variable operations:

|                                                          |                                                                                                                                                               |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| `void SetValue(string variableName, string stringValue)` |                                                                                     Associate the string `stringValue` with the variable named `variableName` |
| `void SetValue(string variableName, float floatValue)`   |                                                                                       Associate the float `floatValue` with the variable named `variableName` |
| `void SetValue(string variableName, bool boolValue)`     |                                                                                      Associate the boolean `boolValue` with the variable named `variableName` |
| `bool TryGetValue<T>(string variableName, out T result)` | Retrieve the variable named `variableName` as a type `T` and store it into the `result`out parameter. Return `true` if this was possible or `false` otherwise |

These handle most variable storage interactions. You'll also need two utility methods:

|                                      |                                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------------: |
| `void Clear()`                       |                                  Delete all variables from the variable storage |
| `bool Contains(string variableName)` | Return `true` if there is a variable named `variableName` in the variable store |

Finally, implement two bulk storage and retrieval methods used by the built-in persistence functions and editor utilities:

|                                                                                                                                                    |                                                                                                                                                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| `void SetAllVariables(Dictionary<string, float> floats, Dictionary<string, string> strings, Dictionary<string, bool> bools, bool clear = true)`    | Is a bulk setter for all variables. The three dictionary parameters represent each of the `floats`, `strings`, and `bools` needed to be saved. The `clear` parameter indicates if the variable storage should clear itself before applying the bulk set. |
| `(Dictionary<string, float> FloatVariables, Dictionary<string, string> StringVariables, Dictionary<string, bool> BoolVariables) GetAllVariables()` |                                                   Returns all variables in the store. Returns them as a 3-tuple of dictionaries, each dictionary should contain all variables in the store of it's type, with the types being `float`, `string`, `bool`. |

#### Smart Variables

Yarn Spinner v3 introduces Smart Variables, which function like computed properties in C#. Their values are determined by running Yarn code rather than direct variable lookup.

When implementing your own variable storage, you don't need to handle smart variables directly. The `VariableStorageBehaviour` base class already provides this functionality, which your subclass inherits automatically. We strongly recommend against overriding this behavior unless you fully understand the implementation details.

#### Example

Let's integrate Yarn variables into an existing game state system with some interesting complexities. Our example system has two key characteristics that make integration challenging:

1. It stores the complete history of variable changes rather than just current values, perhaps for supporting time-rewind mechanics or achievement tracking.
2. It uses indexing instead of key storage to minimize save file size. Keys can consume significant storage space—in our example with variables like `$knows_fred = true`, `$gold_coins = 2`, and `$player_name = "Alice"`, keys represent approximately 60% of the data. In games with thousands of variables, the key-to-value ratio can reach 10:1. Our system avoids storing keys altogether while still handling key-based lookups.

Our existing system stores game state in an array of `IConvertible` Lists, adding a new entry to the appropriate list whenever a value changes and returning the last entry when a value is requested.

{% hint style="info" %}
If you're unfamiliar with perfect hashing, you might wonder how we can use indices without storing keys. Perfect hashing creates collision-free mappings from keys to array indices. Unlike standard hashing, it guarantees unique indices for each key, allowing direct array access without comparison operations.

The main limitation is that all keys must be known in advance, but since our variable set is fixed after development, this works perfectly. Our implementation uses the Hash, Displace, and Compress algorithm **LINK** with Laurent Dupuis's C# implementation **LINK**
{% endhint %}

Here's our existing system:

```csharp
public class GameStateManager : Monobehaviour
{
    private List<IConvertible>[] gameState;
    private MinPerfectHash hashFunction;

    public void Initialise(string[] keys) { ... }

    public bool TryGetValues<T>(string variableName, out T[] result) { ... }
    public T[] ValuesAt<T>(int index) { ... }

    public void AddValue(string variableName, IConvertible value) {}
    public void AddValueAt(int index, IConvertible value) {}

    public void Rollback(string variableName) { ... }
    public void RollbackAt(int index) { ... }

    public void Clear() { ... }
}
```

Let's examine key methods, starting with initialization:

```csharp
public void Initialise(string[] keys)
{
    // generate a new hash function for the specific list of keys
    var keyHashGenerator = new VariableHashKeySource(keys);
    hashFunction =  MinPerfectHash.Create(keyHashGenerator, 1);
    // now we make the values array of the size of the hash function
    gameState = new List<IConvertible>[hashFunction.N];
}
```

This creates a perfect hash function for our keys and initializes the state array. Next, let's see how it adds values:

```csharp
public void AddValue(string variableName, IConvertible value)
{
    // if we don't have a hash function we can't find the index for where to add the new value
    if (hashFunction == null)
    {
        throw new InvalidOperationException();
    }

    var index = hashFunction.IndexOf(variableName);
    var values = gameState[index];

    // if we have no list at this index that means that the key is invalid
    if (values == null)
    {
        throw new ArgumentException();
    }

    // finally we can now add the new value to the list
    values.Add(value);
    gameState[index] = values;
}
```

After validating the key, this appends the new value to the list for that index. Finally, here's value retrieval:

```csharp
public bool TryGetValues<T>(string variableName, out T[] result)
{
    if (hashFunction == null)
    {
        result = default;
        return false;
    }

    var index = hashFunction.IndexOf(variableName);
    if (gameState[index] == null)
    {
        result = default;
        return false;
    }

    // adding all the elements to an array, letting you see the variable history
    var extant = gameState[index];
    T[] values = new T[extant.Count];
    for (int i = 0; i < extant.Count; i++)
    {
        values[i] = (T)extant[i];
    }

    result = values;
    return true;
}
```

After validating the key, this returns a copy of all values for that variable.

**Conforming to VariableStorageBehaviour**

Now let's adapt this system to work with Yarn Spinner by implementing `VariableStorageBehaviour`:

```csharp
public class GameStateManager : Yarn.Unity.VariableStorageBehaviour
{
    private List<IConvertible>[] gameState;
    private MinPerfectHash hashFunction;

    public Yarn.Unity.YarnProject project;

    private List<IConvertible>[] gameState;
    private MinPerfectHash hashFunction;

    public void Initialise(string[] keys) { ... }

    public bool TryGetValues<T>(string variableName, out T[] result) { ... }
    public T[] ValuesAt<T>(int index) { ... }

    public void AddValue(string variableName, IConvertible value) {}
    public void AddValueAt(int index, IConvertible value) {}

    public void Rollback(string variableName) { ... }
    public void RollbackAt(int index) { ... }

    public override void Clear() { ... }
    
    public override void SetValue(string variableName, string stringValue) { ... }
    public override void SetValue(string variableName, float floatValue) { ... }
    public override void SetValue(string variableName, bool boolValue) { ... }

    public override bool TryGetValue<T>(string variableName, out T result) { ... }

    public override bool Contains(string variableName) { ... }
    public override void SetAllVariables(Dictionary<string, float> floats, Dictionary<string, string> strings, Dictionary<string, bool> bools, bool clear = true) { ... }
    public override (Dictionary<string, float> FloatVariables, Dictionary<string, string> StringVariables, Dictionary<string, bool> BoolVariables) GetAllVariables() { ... }
}
```

Besides changing the base class to `VariableStorageBehaviour`, we've added a `YarnProject` reference for accessing default values and implemented the required methods. Let's modify the `Initialise` method first:

```csharp
public void Initialise(string[] keys)
{
    // if we don't have a project we will have to abort initialisation
    if (project == null)
    {
        Debug.LogError("Unable to initialise variable storage as there is no Yarn Project set");
        return;
    }

    // getting the initial values from the project
    // and merging that with the rest of the game keys
    var initialValues = project.InitialValues;
    List<string> yarnKeys = new();
    yarnKeys.AddRange(keys);
    yarnKeys.AddRange(initialValues.Keys);
    
    // generate a new hash function for the specific list of keys
    var keyHashGenerator = new VariableHashKeySource(yarnKeys.ToArray());
    hashFunction =  MinPerfectHash.Create(keyHashGenerator, 1);
    // now we make the values array of the size of the hash function
    gameState = new List<IConvertible>[hashFunction.N];

    // now we can add into the array the default yarn values
    foreach (var pair in initialValues)
    {
        uint index = hashFunction.IndexOf(pair.Key);
        gameState[index] = new List<IConvertible>()
        {
            pair.Value,
        };
    }
}
```

We now include Yarn variable names in our key list and initialize them with their default values. Next, let's implement the `SetValue` methods:

```csharp
public override void SetValue(string variableName, string stringValue)
{
    AddValue(variableName, stringValue);
}
public override void SetValue(string variableName, float floatValue)
{
    AddValue(variableName, floatValue);
}
public override void SetValue(string variableName, bool boolValue)
{
    AddValue(variableName, boolValue);
}
```

Since we already have a method for adding values by name, implementation is straightforward. Now for `TryGetValue`:

```csharp
public override bool TryGetValue<T>(string variableName, out T result)
{
    // if we don't have a hash function we can't find the index
    if (hashFunction == null)
    {
        result = default;
        return false;
    }

    // getting the index of the variable name
    var index = hashFunction.IndexOf(variableName);
    var values = gameState[index];
    
    // if we have no value at that index we also can't return it
    if (values == null)
    {
        result = default;
        return false;
    }

    // grabbing the last element
    var value = values[^1];
    // checking it is actually of type T
    if (!typeof(T).IsAssignableFrom(value.GetType()))
    {
        result = default;
        return false;
    }

    // returning it
    result = (T)value;
    return true;
}
```

While we could have used the existing `TryGetValues` method and just returned the last element, this implementation shows a more direct approach. It validates the key, retrieves the latest value, and returns it after type checking.

The `Contains` method presents an interesting challenge since we don't store keys directly:

```csharp
public override bool Contains(string variableName)
{
    // if we don't have a hash function we can't see if we have a value for that key
    if (hashFunction == null)
    {
        throw new InvalidOperationException();
    }

    var index = hashFunction.IndexOf(variableName);
    var values = gameState[index];

    return values == null;
}
```

This leverages a characteristic of our perfect hash function: some array slots remain null by default because creating a minimal perfect hash can be challenging. Variables that don't exist will hash to empty slots, allowing us to use a null check to determine existence.

Finally, let's implement the bulk operations. First, `SetAllVariables`:

```csharp
public override void SetAllVariables(Dictionary<string, float> floats, Dictionary<string, string> strings, Dictionary<string, bool> bools, bool clear = true)
{
    if (hashFunction == null)
    {
        throw new InvalidOperationException();
    }

    foreach (var pair in floats)
    {
        AddValue(pair.Key, pair.Value);
    }
    foreach (var pair in bools)
    {
        AddValue(pair.Key, pair.Value);
    }
    foreach (var pair in strings)
    {
        AddValue(pair.Key, pair.Value);
    }
}
```

This simply iterates through each variable collection and adds values individually. While not the most efficient approach, it's adequate for this infrequently-called method.

Lastly, `GetAllVariables`:

```csharp
public override (Dictionary<string, float> FloatVariables, Dictionary<string, string> StringVariables, Dictionary<string, bool> BoolVariables) GetAllVariables()
{
    if (hashFunction == null)
    {
        throw new InvalidOperationException();
    }
    if (project == null)
    {
        throw new InvalidOperationException();
    }

    Dictionary<string, float> allFloats = new();
    Dictionary<string, string> allStrings = new();
    Dictionary<string, bool> allBools = new();
    foreach (var key in project.InitialValues.Keys)
    {
        var index = hashFunction.IndexOf(key);
        var values = gameState[index];

        // if we have no list at this index that means that the key is invalid
        if (values == null)
        {
            continue;
        }

        var value = values[^1];
        if (value is bool v)
        {
            allBools[key] = v;
            continue;
        }
        if (value is float f)
        {
            allFloats[key] = f;
            continue;
        }
        if (value is string s)
        {
            allStrings[key] = s;
            continue;
        }
    }

    return (allFloats, allStrings, allBools);
}
```

Since we don't store keys directly, we use the project's `InitialValues` to iterate through known Yarn variables, retrieve their current values, and sort them by type into the appropriate dictionaries.

#### **And we're done!**

With these additions, we've successfully adapted our existing game state system to serve as a Yarn Spinner variable storage provider. The integration required minimal additional code, mostly consisting of adapters that call into our existing methods. This demonstrates how straightforward it can be to integrate Yarn Spinner with your existing architecture.

For the complete example code, see [the sample project](https://github.com/YarnSpinnerTool/CustomVariableStorage).
