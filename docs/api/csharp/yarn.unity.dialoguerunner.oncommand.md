# onCommand

Field in [DialogueRunner](yarn.unity.dialoguerunner.md)

## Summary

A [StringUnityEvent](yarn.unity.dialoguerunner.stringunityevent.md) that is called when a [Command](yarn.command.md) is received.

```csharp
public StringUnityEvent onCommand;
```

## Remarks

Use this method to dispatch a command to other parts of your game. This method is only called if the [Command](yarn.command.md) has not been handled by a command handler that has been added to the [DialogueRunner](yarn.unity.dialoguerunner.md), or by a method on a `UnityEngine.MonoBehaviour` in the scene with the attribute [YarnCommandAttribute](yarn.unity.yarncommandattribute.md).

{% hint style="info" %}
When a command is delivered in this way, the [DialogueRunner](yarn.unity.dialoguerunner.md) will not pause execution. If you want a command to make the DialogueRunner pause execution, see `AddCommandHandler(string, CommandHandler)`.
{% endhint %}

This method receives the full text of the command, as it appears between the `<<` and `>>` markers.

## See Also

* AddCommandHandler(string, CommandHandler)
* AddCommandHandler(string, CommandHandler)
* [YarnCommandAttribute](yarn.unity.yarncommandattribute.md): An attribute that marks a method on an object as a command.
