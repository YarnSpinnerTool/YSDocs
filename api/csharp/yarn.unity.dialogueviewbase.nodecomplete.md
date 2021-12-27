# DialogueViewBase.NodeComplete(string,Action)

Method in [DialogueViewBase](/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the
end of a node has been reached.


```csharp
public virtual void NodeComplete(string nextNode, Action onComplete)
```

## Remarks


This method may be called multiple times before  <a href="yarn.unity.dialogueviewbase.dialoguecomplete.md">DialogueComplete()</a>  is called. If this method returns
<code>Dialogue.HandlerExecutionType.ContinueExecution</code> ,
do not call the  <code>onComplete</code>  method.

The default implementation does nothing.


## Parameters

|Name|Description|
|:---|:---|
|`string` nextNode|The name of the next node that is being entered.|
|`Action` onComplete|A method that should be called to /// indicate that the DialogueRunner should continue executing.|

