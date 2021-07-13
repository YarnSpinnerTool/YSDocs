# Add\(YarnProgram\)

Adds a program, and parses and adds the contents of the program's string table to the DialogueRunner's combined string table.

```csharp
public void Add(YarnProgram scriptToLoad)
```

### Remarks

This method calls `AddStringTable(YarnProgram)` to load the string table for the current localisation. It selects the appropriate string table based on the value of `textLanguage`.

### Parameters

| Parameter | Description |
| :--- | :--- |
| `YarnProgram` scriptToLoad | The `YarnProgram` to load. |

### Source

Defined in [Unity/Assets/YarnSpinner/Scripts/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner/blob/develop/Unity/Assets/YarnSpinner/Scripts/DialogueRunner.cs#L146), line 146.

### Assembly 

YarnSpinner.Unity.dll



