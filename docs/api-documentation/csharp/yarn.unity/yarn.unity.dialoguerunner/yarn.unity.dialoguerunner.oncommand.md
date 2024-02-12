# onCommand

Field in [DialogueRunner](./)

## Summary

A [StringUnityEvent](yarn.unity.dialoguerunner.stringunityevent.md) that is called when a [Command](../../yarn/yarn.command/) is received.

```csharp
public StringUnityEvent onCommand;
```

## Remarks

Use this method to dispatch a command to other parts of your game. This method is only called if the [Command](../../yarn/yarn.command/) has not been handled by a command handler that has been added to the [DialogueRunner](./), or by a method on a `UnityEngine.MonoBehaviour` in the scene with the attribute [YarnCommandAttribute](../yarn.unity.yarncommandattribute/).

{% hint style="info" %}
When a command is delivered in this way, the [DialogueRunner](./) will not pause execution. If you want a command to make the DialogueRunner pause execution, see `AddCommandHandler(string, CommandHandler)`.
{% endhint %}

This method receives the full text of the command, as it appears between the `<<` and `>>` markers.

## See Also

* AddCommandHandler(string, CommandHandler)
* AddCommandHandler(string, CommandHandler)
* [YarnCommandAttribute](../yarn.unity.yarncommandattribute/): An attribute that marks a method on an object as a command.
