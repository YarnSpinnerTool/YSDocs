# DialogueRunner

The DialogueRunner component acts as the interface between your game and Yarn Spinner.

```csharp
[AddComponentMenu("Scripts/Yarn Spinner/Dialogue Runner")]
public class DialogueRunner : MonoBehaviour, ILineLocalisationProvider
```

### Methods

| Class |  |
| :--- | :--- |
| Add\(YarnProgram\) | Adds a program, and parses and adds the contents of the program's string table to the DialogueRunner's combined string table. |
| AddCommandHandler\(String, DialogueRunner.BlockingCommandHandler\) | Adds a command handler. Dialogue will pause execution after the command is called. |

### Source

Defined in [Unity/Assets/YarnSpinner/Scripts/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner/blob/develop/Unity/Assets/YarnSpinner/Scripts/DialogueRunner.cs#L44), line 44.



