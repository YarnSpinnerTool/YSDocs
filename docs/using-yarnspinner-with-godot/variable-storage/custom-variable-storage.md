# Creating Custom Variable Storage Components

Every game's data storage requirements are different. For this reason, Yarn Spinner is designed to make it straightforward to create your own custom component for managing how Yarn scripts store and load variables in ways that work with the other parts of your game. 

Custom Variable Storage components are subclasses of the abstract class `VariableStorageBehaviour`. To implement your own, you need to implement the following methods:

```csharp
public bool TryGetValue<T>(string variableName, out T result);
public void SetValue(string variableName, string stringValue);
public void SetValue(string variableName, float floatValue);
public void SetValue(string variableName, bool boolValue);
public void Clear();
public bool Contains(string variableName);
```

For a tutorial on how to build an entirely custom variable storage system, see below. It is written for the Unity plugin, but variable storage in the Godot plugin works almost identically, so keep the following differences in mind while reading. 

* You will install any referenced libraries via your .csproj file rather than Unity's assembly definitions or its package manager.
* Change any instances of `using Yarn.Unity;` to `using YarnSpinnerGodot;`.
* Change any instances of `using UnityEngine;` to `using Godot;`.
* Rather than the Unity-specific `Application.persistentDataPath`, you can use the prefix `user://` to save your database `.sqlite` file to the player's machine. 

[Yarn Variables and Custom Variable Storage](../../../guides/yarn-variables-and-variable-storage.md).