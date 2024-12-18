# Yarn Variables and Custom Variable Storage

When writing Yarn scripts, variables come in handy for storing state and user preferences that can persist and impact story dialogue or choices later on. When using Yarn Spinner for Unity, variables from Yarn scripts can be accessed in C# code by using the provided `InMemoryVariableStorage`, which acts as a simple dictionary to store variable names with their current values.

This looks something like this:

{% code title="Example.yarn" %}
```shell
<<set $testVariable = 1>>
```
{% endcode %}

{% code title="Example.cs" %}
```csharp
variableStorage = GameObject.FindObjectOfType<InMemoryVariableStorage>();
float testVariable;
variableStorage.TryGetValue("$testVariable", out testVariable);
variableStorage.SetValue("$testVariable", testVariable + 1);
```
{% endcode %}

This allows Yarn types `String`, `Number` and `Boolean` to be stored in memory, and then accessed by this wrapper class that converts them to the C# equivalents `string`, `float` and `bool`, ready for use in your code.

`InMemoryVariableStorage` is flexible and extensible, and has utilities for things such as initialising with default variables declared, or serialising to and from JSON. But what if you want to add very custom behaviour to how variables are stored? To keep values somewhere other than in memory, or add side effects to certain operations in a way that wouldn’t work by just extending this default variable storage? Well, you can **define your own**.

## What makes a Variable Storage?

Like other parts of the Unity API for Yarn Spinner, Variable Storage is made possible with the use of **abstract classes**. [Abstract classes in C#](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/abstract) work a little bit like interfaces or protocols in other languages, in that they define a class that cannot be instantiated but can be used to make others. In this way, an abstract class is like a set of constraints for some hypothetical subclass you will define later: it can declare certain methods which your subclass **must** implement for it to work, and it can contain implementations or values of its own which act as **defaults** that you may or may not choose to override.

In Yarn Spinner for Unity, `VariableStorageBehaviour` is an abstract class that can be inherited from. It specifies the methods which Yarn Spinner may call at runtime, which are expected to be dealt with in your implementation:

|                                                     |                                                                                                                                                                                     |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `TryGetValue(string variableName, out T result)`    | Look to see if `variableName` exists and can be cast to the given type and, if so, return its value.                                                                                |
| `SetValue(string variableName, string stringValue)` | Store the value `stringValue` and somehow attribute it with the key `variableName`.                                                                                                 |
| `SetValue(string variableName, float floatValue)`   | Store the value `floatValue` and somehow attribute it with the key `variableName`.                                                                                                  |
| `SetValue(string variableName, bool boolValue)`     | Store the value `boolValue` and somehow attribute it with the key `variableName`.                                                                                                   |
| `Clear()`                                           | Remove, release or otherwise un-attribute all previously set variable names, such that calling `TryGetValue()` without first calling `SetValue()` with the same key would now fail. |
| `Contains(string variableName)`                     | Return whether a particular `variableName` exists as a key in the storage at this moment.                                                                                           |

Now, Yarn Spinner **does not care** how your custom `VariableStorageBehaviour` works beyond that. It simply assumes that you are doing something sensible, and that your subclass will provide the functionality it expects. Some of those expectations cannot be constrained in code, like the required method declarations can, so there is a level of trust here that you (as the implementer of this black box subclass which Yarn Spinner has never seen) will:

1. **Actually store values somewhere.** Your code will still compile if your `SetValue()` methods are empty or otherwise throw away the values they are given, but this will mean your `TryGetValue()` methods will never be able to work.
2. **Actually get the right value for the given key.** Your code will still compile if your `TryGetValue()` methods return random values from the aether, but this will make your use of these variables in your Yarn script effectively nonsensical. Likewise if you allow setting of multiple values with the same key.
3. **Actually get rid of values when asked to.** Your code will still compile if your `Clear()` method does nothing, but this means that Yarn script progress or state may never be reset correctly.
4. **Actually check if a key already exists.** Your code will still compile if your `Contains()` method always returns false, but this will lead to overwriting existing values the next time someone tries to `SetValue()` a seemingly unused key that already had a value.

![Artist’s Impression of a malicious custom VariableStorage that does not look after its values.](../../.gitbook/assets/IMG\_0037.PNG)

So let’s assume you are not some chaos demon and you actually want to make a Variable Storage that works the way the Yarn Spinner runtime expects, so that you get variables that **actually work.** You need:

* A way to **store values** of the given types, each associated with a **unique key**.
* A way to **get those values back**, as the expected type.
* A way to **get rid** of all the previously stored values.

If you were a masochist, you could write a class whose `SetValue()` method printed out the given key and value on a piece of paper, `Contains()` and `TryGetValue()` methods that took a snapshot with a camera placed above the printer and read the values back, and a `Clear()` method that pushed the paper from the printer tray into a shredder. Yarn Spinner would not care, because it would still **do those three things** (though probably unreliably, and with some storage limitations).

Some more typical examples of things that gamemakers have wanted their variable storage to do are:

* Instead of storing variables in memory in a dictionary, store them on disk or in a database.
* Instead of just setting values in the Variable Storage when asked, also update some corresponding variables on the C# side or call a UnityEvent to notify other components that a value has changed.
* Instead of simply getting and setting values, run them via some sanitation or transformation, or even interface with an external API.

So let’s break down how you would go about implementing one of those more sensible ideas...

## Let’s make a custom Variable Storage!

In this example, let’s replace the default Variable Storage implementation with one that stores values in a SQL database. The example code shown makes use of the [sqlite-net](https://github.com/praeclarum/sqlite-net) library—an open source .Net API for SQL—for the creation of a database and tables, but uses vanilla SQL query strings in place of the convenience bindings which are specific to that library.

{% hint style="warning" %}
SQL is a **domain-specific language** and set of related frameworks that allow the creation and manipulation of **relational databases**. This will not be a guide to SQL, as there are many good ones already out there, but the TL;DR of SQL is: data is stored in **tables**, each column has a **name** and a **type**, each row is an **entry**, and some entries may reference entries in **other tables** that hold related information. **SQL queries** can be used to connect information from across tables, to get the fields of information you want.
{% endhint %}

To begin, we need to make a custom class for our new Variable Storage, which should inherit from the `VariableStorageBehaviour` abstract class.

```csharp
using UnityEngine;
using Yarn.Unity;
using SQLite;

public class SQLVariableStorage : VariableStorageBehaviour {}
```

If you are following along, your IDE will probably complain at this point, because this empty class does not fulfil the requirements defined by the abstract superclass. To conform, we need **at least** the six methods listed earlier.

```csharp
public override bool TryGetValue<T>(string variableName, out T result) {}
public override void SetValue(string variableName, string stringValue) {}
public override void SetValue(string variableName, float floatValue) {}
public override void SetValue(string variableName, bool boolValue) {}
public override void Clear() {}
public override bool Contains(string variableName) {}
```

So let’s have a think about how each of these would need to work, given a backing of SQL. We need to be able to **insert values** into tables, check if a **value exists** in tables with the given key, return the **corresponding value** for a given key, and **remove all entries** from tables.

But first, before any values can be set, the database needs to already exist. Set up like this conventionally occurs in the `Start()` method:

```csharp
void Start() {
        // pick a place on disk for the database to save to
        string path = Application.persistentDataPath + "/db.sqlite";
        // create a new database connection to speak to it
        db = new SQLiteConnection(path);
        // TODO: create the tables we need ??
        // ...
}
```

Next, to create the tables we need to store values in, we need to declare a class that represents a single entry. Its class name will becomes the **table name** by default, and its field names and types will become the **column names and types**. Because each column can only hold one type, we’ll need **one table for each type**.

These classes would look something like this:

```csharp
public class YarnString {
	[PrimaryKey]
	public string key { get; set; }
	public string value { get; set; }
}
public class YarnFloat {
	[PrimaryKey]
	public string key { get; set; }
	public float value { get; set; }
}
public class YarnBool {
	[PrimaryKey]
	public string key { get; set; }
	public bool value { get; set; }
}
```

The column that will be used to reference or fetch values—and is thus required to be **unique within that table**—is specified by the `[PrimaryKey]` decorator.

Then, to create an empty table in the database, we can call the database connector’s `CreateTable()` method with the class we want to represent.

```csharp
void Start() {
        // pick a place on disk for the database to save to
        string path = Application.persistentDataPath + "/db.sqlite";
        // create a new database connection to speak to it
        db = new SQLiteConnection(path);
        // create the tables we need
        db.CreateTable<YarnString>();
        db.CreateTable<YarnFloat>();
        db.CreateTable<YarnBool>();
}
```

{% hint style="info" %}
Those familiar with SQL may notice that these tables do not reference each other and thus this is not an ideal use case for SQL. But this is a minimal example for a method that would be more effectively used in larger games with more complex schemas for their data storage or persistence.
{% endhint %}

Now we can begin filling out our empty method declarations. Beginning with the easiest, `Clear()` is just a matter of telling each table in the database to remove all its entries. The query for this is `DELETE * FROM TableName`, where the `*` means all entries. Executing a query on the database is as simple as calling `Execute()` on the database connector with a string parameter of the desired query.

```csharp
public override void Clear() {
    db.Execute("DELETE * FROM YarnString;");
    db.Execute("DELETE * FROM YarnBool;");
    db.Execute("DELETE * FROM YarnFloat;");
}
```

Now to the fiddliest method, `TryGetValue()` is the method that needs to figure out whether a value exists for the given key and, if so, return it **as the correct type**. This requires a little bit of [C# generics](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/types/generics).

First we need to do some switching of which table we need to look for the value in:

```csharp
public override bool TryGetValue<T>(string variableName, out T result) {
    if (typeof(T) == typeof(string)) {
        // TODO: search YarnString for variableName
    } else if (typeof(T) == typeof(bool)) {
        // TODO: search YarnBool for variableName
    } else if (typeof(T) == typeof(float)) {
        // TODO: search YarnFloat for variableName
    }
    result = default(T);
    return false;
}
```

Then, within each, we should look for that key within the corresponding table. To return only the value from any row that matches our variable name we specify `Select ColumnName FROM TableName WHERE (conditions to match)`.

{% hint style="danger" %}
To make sure the compiler knows what `T` is at compile time, results must be cast to `object` and then back to `T` (thanks, C#!).
{% endhint %}

```csharp
public override bool TryGetValue<T>(string variableName, out T result) {
    string query = "";
    List<object> results = null;
    // try to get a value from the given table, as a generic object
    if (typeof(T) == typeof(string)) {
        query = $"SELECT value FROM YarnString WHERE key = {variableName}";
    } // else if ...
    // (other cases go here)
    
    // if a result was found, convert it to type T and assign it
    results = db.Query<object>(query);
    if (results?.Count > 0) {
        result = (T)results[0];
        return true;
    }
    
    // otherwise TryGetValue has failed
    result = default(T);
    return false;
}
```

Next, before we can begin inserting values into tables, we first want to make sure a value doesn’t already exist for that key in another table. We can do this by creating a utility method that uses a lookup query to check if a value exists with that key in a **specific table**. This can take advantage of our `TryGetValue()` implementation:

```csharp
private bool Exists(string variableName, System.Type type) {
    if (type == typeof(string)) {
        string stringResult;
        if (TryGetValue<string>(variableName, out stringResult)) {
            return (stringResult != null);
        }
    } else if (type == typeof(bool)) {
        string boolResult;
        if (TryGetValue<string>(variableName, out boolResult)) {
            return (boolResult != null);
        }
    } else if (type == typeof(float)) {
        string floatResult;
        if (TryGetValue<string>(variableName, out floatResult)) {
            return (floatResult != null);
        }
    }
    return false;
}
```

...which can then also be used as the basis for our `Contains()` method, by checking them all:

```csharp
public override bool Contains(string variableName) {
    return Exists(variableName, typeof(string)) || 
        Exists(variableName, typeof(bool)) || 
        Exists(variableName, typeof(float));
}
```

This utility method then also comes in handy when defining the `SetValue()` methods, which would each look something like this:

```csharp
public override void SetValue(string variableName, string stringValue) {
    // check it doesn't exist already in other table
    if (Exists(variableName, typeof(bool))) {
            throw new System.ArgumentException($"{variableName} is a bool.");
    // check if doesn't exist already in other other table
    } else if (Exists(variableName, typeof(float))) {
            throw new System.ArgumentException($"{variableName} is a float.");
    }
    // if not, insert or update row in this table to the given value
    string query = "INSERT OR REPLACE INTO YarnString (key, value)";
    query += $"VALUES ({variableName}, {stringValue})";
    db.Execute(query);
}
```

{% hint style="danger" %}
In production, you should **always validate and sanitise input** before inserting it into SQL, in case our string value itself contains invalid syntax or partial SQL commands. Otherwise, you may leave yourself open to **SQL injection attacks**.
{% endhint %}

And lo! We should now have a fully functioning SQL-backed custom Variable Storage for Yarn Spinner. Simply replace the Variable Storage component on the `DialogueRunner` game object in your scene to put your custom implementation to work.

As far as Yarn Spinner is concerned, this should behave exactly as the provided `InMemoryVariableStorage` does at runtime, even though **the entire storage model and behaviour has changed**.

Using this simple method of overriding methods in the inbuilt `VariableStorageBehaviour` abstract class, you can make a custom Variable Storage backed by **virtually anything to suit your needs**!

## Where to go to learn more

Check out the [documentation on Variable Storage](https://docs.yarnspinner.dev/using-yarnspinner-with-unity/components/variable-storage) or ask the community in the [Yarn Spinner Discord Server](https://t.co/hp1J7fvEUL)!

{% hint style="success" %}
You can download the full implementation of the script made in this guide [here](https://github.com/YarnSpinnerTool/ExampleProjects/blob/main/UtilityScripts/SQLVariableStorage.cs). Or you may also like to read through the default implementation of `InMemoryVariableStorage` [here](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/main/Runtime/InMemoryVariableStorage.cs).
{% endhint %}
