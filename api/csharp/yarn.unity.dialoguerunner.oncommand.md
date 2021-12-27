# DialogueRunner.onCommand

Field in [DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


A  <a href="yarn.unity.dialoguerunner.stringunityevent.md">StringUnityEvent</a>  that is called when a  <code>Command</code>  is received.


```csharp
public StringUnityEvent onCommand;
```

## Remarks


Use this method to dispatch a command to other parts of your
game. This method is only called if the  <code>Command</code> 
has not been handled by a command handler that has been added
to the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> , or by a method on a  <code>MonoBehaviour</code>  in the scene with the attribute  <a href="yarn.unity.yarncommandattribute.md">YarnCommandAttribute</a> . {{|note|}} When a command is
delivered in this way, the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  will
not pause execution. If you want a command to make the
DialogueRunner pause execution, see  <code>AddCommandHandler(string, CommandHandler)</code> . {{|/note|}}

This method receives the full text of the command, as it
appears between the ` <![CDATA[<<]]> ` and ` <![CDATA[>>]]> `
markers.


## See Also

* AddCommandHandler\(string, CommandHandler)
* AddCommandHandler\(string, CommandHandler)
* [YarnCommandAttribute](/api/csharp/yarn.unity.yarncommandattribute.md): An attribute that marks a method on an object as a  [command]( <![CDATA[ {{<ref "/docs/unity/working-with-commands">}}]]> ).

