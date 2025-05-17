# DialogueRunner.onUnhandledCommand

Field in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


A  <a href="yarn.unity.unityeventstring.md">UnityEventString</a>  that is called when a  <a href="yarn.command.md">Command</a>  is received and no command handler was able to
handle it.


```csharp
public UnityEventString? onUnhandledCommand;
```

## Remarks

<p>
Use this method to dispatch a command to other parts of your game.
This method is only called if the <a href="yarn.command.md">Command</a> has not been
handled by a command handler that has been added to the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>, or by a method on a `UnityEngine.MonoBehaviour` in the scene with the attribute <a href="yarn.unity.yarncommandattribute.md">YarnCommandAttribute</a>.
</p> <p>
{% hint style="hint" %}

When a command is delivered in this way, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will not pause execution. If you want a
command to make the DialogueRunner pause execution, see <a href="yarn.unity.dialoguerunner.addcommandhandler-1.md">AddCommandHandler(string,Delegate)</a>.

{% endhint %}
</p> <p>
This method receives the full text of the command, as it appears
between the `&lt;&lt;` and `&gt;&gt;` markers.
</p>

## See Also

* [DialogueRunner.AddCommandHandler\(string,Delegate\)](/docs/api/csharp/yarn.unity.dialoguerunner.addcommandhandler-1.md): Adds a command handler. Dialogue will pause execution after the command is called.
* [YarnCommandAttribute](/docs/api/csharp/yarn.unity.yarncommandattribute.md): An attribute that marks a method on an object as a command.

