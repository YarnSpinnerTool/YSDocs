# onCommand

A [`DialogueRunner.StringUnityEvent`](../dialoguerunner.stringunityevent.md) that is called when a  is received.

```csharp
public DialogueRunner.StringUnityEvent onCommand
```

## Remarks

Use this method to dispatch a command to other parts of your game. This method is only called if the  has not been handled by a command handler that has been added to the [`DialogueRunner`](./), or by a method on a  in the scene with the attribute [`YarnCommandAttribute`](../yarncommandattribute/).  When a command is delivered in this way, the [`DialogueRunner`](./) will not pause execution. If you want a command to make the DialogueRunner pause execution, see . 

This method receives the full text of the command, as it appears between the `<<` and `>>` markers.

## See Also

* [`YarnCommandAttribute`](../yarncommandattribute/): An attribute that marks a method on a  as a \[command\]\( \).
* [`DialogueRunner.StringUnityEvent`](../dialoguerunner.stringunityevent.md): A type of  that takes a single string parameter.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L172), line 172.

