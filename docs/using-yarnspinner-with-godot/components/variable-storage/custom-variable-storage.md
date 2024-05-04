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
public void SetAllVariables(System.Collections.Generic.Dictionary<string,float> floats, System.Collections.Generic.Dictionary<string,string> strings, System.Collections.Generic.Dictionary<string,bool> bools, bool clear = true);
public (System.Collections.Generic.Dictionary<string,float>,System.Collections.Generic.Dictionary<string,string>,System.Collections.Generic.Dictionary<string,bool>) GetAllVariables();

```

For a tutorial on how to build an entirely custom variable storage system, see
[Yarn Variables and Custom Variable Storage](../guides/yarn-variables-and-variable-storage-godot.md).