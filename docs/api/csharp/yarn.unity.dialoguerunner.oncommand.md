# DialogueRunner.onCommand

Field in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


A  <code>StringUnityEvent</code>  that is called when a  <a href="yarn.command.md">Command</a>  is received.


```csharp
public UnityEventString onCommand;
```

## Remarks

<p>
Use this method to dispatch a command to other parts of your game.
This method is only called if the <a href="yarn.command.md">Command</a> has not been
handled by a command handler that has been added to the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>, or by a method on a <code>UnityEngine.MonoBehaviour</code> in the scene with the attribute <a href="yarn.unity.yarncommandattribute.md">YarnCommandAttribute</a>.
</p> <p>
{% hint style="hint" %}

When a command is delivered in this way, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will not pause execution. If you want a
command to make the DialogueRunner pause execution, see <code>AddCommandHandler(string, CommandHandler)</code>.

{% endhint %}
</p> <p>
This method receives the full text of the command, as it appears
between the <code>&lt;&lt;</code> and <code>&gt;&gt;</code> markers.
</p>

## See Also

* AddCommandHandler\(string, CommandHandler\)
* AddCommandHandler\(string, CommandHandler\)
* [YarnCommandAttribute](/docs/api/csharp/yarn.unity.yarncommandattribute.md): An attribute that marks a method on an object as a command.

